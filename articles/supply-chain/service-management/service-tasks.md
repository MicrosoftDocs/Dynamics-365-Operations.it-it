---
title: "Attività di assistenza tecnica"
description: "Utilizzare le attività di assistenza tecnica per descrivere l'attività da eseguire durante un ordine di assistenza. Tali informazioni possono essere visualizzate sia dai tecnici che dai clienti."
author: ShylaThompson
manager: AnnBe
ms.date: 02/21/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceTask
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: f2538a7b4a4c13a299afb37dd336f2f5d6f36a23
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---

# <a name="service-tasks"></a><span data-ttu-id="2a7c4-104">Attività di assistenza tecnica</span><span class="sxs-lookup"><span data-stu-id="2a7c4-104">Service tasks</span></span>  

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2a7c4-105">Utilizzare le attività di assistenza tecnica per descrivere l'attività da eseguire durante un ordine di assistenza.</span><span class="sxs-lookup"><span data-stu-id="2a7c4-105">Use service tasks to describe the task to be completed during a service order.</span></span>
<span data-ttu-id="2a7c4-106">Tali informazioni possono essere visualizzate sia dai tecnici che dai clienti.</span><span class="sxs-lookup"><span data-stu-id="2a7c4-106">Both technicians and customers can see this information.</span></span>

<span data-ttu-id="2a7c4-107">È possibile creare attività di assistenza tecnica nella pagine **Attività di assistenza tecnica** e associarle a un determinato contratto o ordine di assistenza creando relazioni per tali attività.</span><span class="sxs-lookup"><span data-stu-id="2a7c4-107">You create service tasks in the **Service tasks** page, and you associate service tasks with a specific service agreement or service order by creating service task relations.</span></span> <span data-ttu-id="2a7c4-108">Ogni volta che si crea una relazione di questo tipo, è possibile creare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="2a7c4-108">Every time that you create a service task relation, you can create the following:</span></span>

-  <span data-ttu-id="2a7c4-109">Note interne per l'attività, ad esempio richieste dettagliate relative all'attività di cui il tecnico deve essere informato.</span><span class="sxs-lookup"><span data-stu-id="2a7c4-109">Internal notes for the task, such as detailed technical requests for the task that are important for the technician to know.</span></span>

-  <span data-ttu-id="2a7c4-110">Note esterne che possono essere visualizzate dal cliente.</span><span class="sxs-lookup"><span data-stu-id="2a7c4-110">External notes that the customer can see.</span></span> <span data-ttu-id="2a7c4-111">Potrebbero fornire una descrizione meno tecnica dell'attività da eseguire in base al contratto stipulato tra il cliente e la società di assistenza.</span><span class="sxs-lookup"><span data-stu-id="2a7c4-111">These might provide a less technical explanation of the task that is being completed, according to the agreement between the customer and the service company.</span></span>

<span data-ttu-id="2a7c4-112">Una volta definita una relazione tra un'attività di assistenza tecnica e un ordine o un contratto di assistenza, è possibile specificare tale attività quando si creano le righe per l'ordine o il contratto di assistenza corrente.</span><span class="sxs-lookup"><span data-stu-id="2a7c4-112">When you have set up a service task relation between a service task and a service order or service agreement, you can specify this service task when you create service order lines or service agreement lines for the current service order or service agreement.</span></span>

<span data-ttu-id="2a7c4-113">Quando si generano ordini di assistenza sulla base di un contratto di assistenza, è possibile utilizzare le attività di assistenza tecnica assegnate a ogni riga del contratto per raggruppare le righe dell'ordine di assistenza in ordini di assistenza.</span><span class="sxs-lookup"><span data-stu-id="2a7c4-113">When you generate service orders from a service agreement, you can use the service tasks that are assigned to each service agreement line to group service order lines into service orders.</span></span>

## <a name="create-a-service-task"></a><span data-ttu-id="2a7c4-114">Creare un'attività di assistenza tecnica</span><span class="sxs-lookup"><span data-stu-id="2a7c4-114">Create a service task</span></span>

1. <span data-ttu-id="2a7c4-115">Fare clic su **Gestione assistenza** \> **Impostazione** \> **Attività di assistenza tecnica**.</span><span class="sxs-lookup"><span data-stu-id="2a7c4-115">Click **Service management** \> **Setup** \> **Service tasks**.</span></span>
2. <span data-ttu-id="2a7c4-116">Creare una nuova riga.</span><span class="sxs-lookup"><span data-stu-id="2a7c4-116">Create a new line.</span></span>
3. <span data-ttu-id="2a7c4-117">Immettere l'ID e la descrizione del servizio.</span><span class="sxs-lookup"><span data-stu-id="2a7c4-117">Enter the service ID and description.</span></span>

## <a name="example"></a><span data-ttu-id="2a7c4-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="2a7c4-118">Example</span></span>

<span data-ttu-id="2a7c4-119">Un tecnico deve effettuare due interventi su una scatola ingranaggi (oggetto assistenza GB-1234) presso il cliente.</span><span class="sxs-lookup"><span data-stu-id="2a7c4-119">A technician must complete two jobs on a gearbox (service object GB-1234) at a customer site.</span></span> <span data-ttu-id="2a7c4-120">Per tale cliente viene creato un contratto di assistenza e agli interventi vengono associate numerose transazioni.</span><span class="sxs-lookup"><span data-stu-id="2a7c4-120">A service agreement is created for the customer, and several transactions are associated with the jobs.</span></span> <span data-ttu-id="2a7c4-121">Di seguito sono riportati il contratto di assistenza e le relative righe per i due interventi:</span><span class="sxs-lookup"><span data-stu-id="2a7c4-121">The service agreement and service agreement lines for the two jobs are as follows:</span></span>

### <a name="service-agreement"></a><span data-ttu-id="2a7c4-122">Contratto di assistenza</span><span class="sxs-lookup"><span data-stu-id="2a7c4-122">Service agreement</span></span>

| <span data-ttu-id="2a7c4-123">Project</span><span class="sxs-lookup"><span data-stu-id="2a7c4-123">Project</span></span> | <span data-ttu-id="2a7c4-124">Contratto di assistenza</span><span class="sxs-lookup"><span data-stu-id="2a7c4-124">Service agreement</span></span> | <span data-ttu-id="2a7c4-125">descrizione</span><span class="sxs-lookup"><span data-stu-id="2a7c4-125">Description</span></span>                                  | <span data-ttu-id="2a7c4-126">Raggruppa</span><span class="sxs-lookup"><span data-stu-id="2a7c4-126">Group</span></span>   |
|---------|-------------------|----------------------------------------------|---------|
| <span data-ttu-id="2a7c4-127">9012</span><span class="sxs-lookup"><span data-stu-id="2a7c4-127">9012</span></span>    | <span data-ttu-id="2a7c4-128">000008\_001</span><span class="sxs-lookup"><span data-stu-id="2a7c4-128">000008\_001</span></span>       | <span data-ttu-id="2a7c4-129">Controllo e sostituzione di routine – GB-1234</span><span class="sxs-lookup"><span data-stu-id="2a7c4-129">Inspection and routine replacement – GB-1234</span></span> | <span data-ttu-id="2a7c4-130">Gratifiche</span><span class="sxs-lookup"><span data-stu-id="2a7c4-130">Premium</span></span> |

### <a name="service-agreement-lines"></a><span data-ttu-id="2a7c4-131">Righe contratto di assistenza</span><span class="sxs-lookup"><span data-stu-id="2a7c4-131">Service agreement lines</span></span>

| <span data-ttu-id="2a7c4-132">descrizione</span><span class="sxs-lookup"><span data-stu-id="2a7c4-132">Description</span></span>             | <span data-ttu-id="2a7c4-133">Tipo di transazione</span><span class="sxs-lookup"><span data-stu-id="2a7c4-133">Transaction type</span></span> | <span data-ttu-id="2a7c4-134">Oggetto assistenza</span><span class="sxs-lookup"><span data-stu-id="2a7c4-134">Service object</span></span> | <span data-ttu-id="2a7c4-135">Attività di assistenza tecnica</span><span class="sxs-lookup"><span data-stu-id="2a7c4-135">Service task</span></span> |
|-------------------------|------------------|----------------|--------------|
| <span data-ttu-id="2a7c4-136">Controllo e pulizia</span><span class="sxs-lookup"><span data-stu-id="2a7c4-136">Inspection and cleaning</span></span> | <span data-ttu-id="2a7c4-137">Ore</span><span class="sxs-lookup"><span data-stu-id="2a7c4-137">Hour</span></span>             | <span data-ttu-id="2a7c4-138">GB-1234</span><span class="sxs-lookup"><span data-stu-id="2a7c4-138">GB-1234</span></span>        | <span data-ttu-id="2a7c4-139">I/C - GB1234</span><span class="sxs-lookup"><span data-stu-id="2a7c4-139">I/C - GB1234</span></span> |
| <span data-ttu-id="2a7c4-140">Travel</span><span class="sxs-lookup"><span data-stu-id="2a7c4-140">Travel</span></span>                  | <span data-ttu-id="2a7c4-141">Expense</span><span class="sxs-lookup"><span data-stu-id="2a7c4-141">Expense</span></span>          | <span data-ttu-id="2a7c4-142">GB-1234</span><span class="sxs-lookup"><span data-stu-id="2a7c4-142">GB-1234</span></span>        | <span data-ttu-id="2a7c4-143">I/C - GB1234</span><span class="sxs-lookup"><span data-stu-id="2a7c4-143">I/C - GB1234</span></span> |
| <span data-ttu-id="2a7c4-144">Materiali</span><span class="sxs-lookup"><span data-stu-id="2a7c4-144">Materials</span></span>               | <span data-ttu-id="2a7c4-145">Articolo</span><span class="sxs-lookup"><span data-stu-id="2a7c4-145">Item</span></span>             | <span data-ttu-id="2a7c4-146">GB-1234</span><span class="sxs-lookup"><span data-stu-id="2a7c4-146">GB-1234</span></span>        | <span data-ttu-id="2a7c4-147">I/C - GB1234</span><span class="sxs-lookup"><span data-stu-id="2a7c4-147">I/C - GB1234</span></span> |
| <span data-ttu-id="2a7c4-148">Sostituzione di routine</span><span class="sxs-lookup"><span data-stu-id="2a7c4-148">Routine replacement</span></span>     | <span data-ttu-id="2a7c4-149">Ore</span><span class="sxs-lookup"><span data-stu-id="2a7c4-149">Hour</span></span>             | <span data-ttu-id="2a7c4-150">GB-1234</span><span class="sxs-lookup"><span data-stu-id="2a7c4-150">GB-1234</span></span>        | <span data-ttu-id="2a7c4-151">RR - GB1234</span><span class="sxs-lookup"><span data-stu-id="2a7c4-151">RR - GB1234</span></span>  |
| <span data-ttu-id="2a7c4-152">GR-1</span><span class="sxs-lookup"><span data-stu-id="2a7c4-152">GR-1</span></span>                    | <span data-ttu-id="2a7c4-153">Articolo</span><span class="sxs-lookup"><span data-stu-id="2a7c4-153">Item</span></span>             | <span data-ttu-id="2a7c4-154">GB-1234</span><span class="sxs-lookup"><span data-stu-id="2a7c4-154">GB-1234</span></span>        | <span data-ttu-id="2a7c4-155">RR - GB1234</span><span class="sxs-lookup"><span data-stu-id="2a7c4-155">RR - GB1234</span></span>  |
| <span data-ttu-id="2a7c4-156">GR-5</span><span class="sxs-lookup"><span data-stu-id="2a7c4-156">GR-5</span></span>                    | <span data-ttu-id="2a7c4-157">Articolo</span><span class="sxs-lookup"><span data-stu-id="2a7c4-157">Item</span></span>             | <span data-ttu-id="2a7c4-158">GB-1234</span><span class="sxs-lookup"><span data-stu-id="2a7c4-158">GB-1234</span></span>        | <span data-ttu-id="2a7c4-159">RR - GB1234</span><span class="sxs-lookup"><span data-stu-id="2a7c4-159">RR - GB1234</span></span>  |

<span data-ttu-id="2a7c4-160">Alle righe del contratto di assistenza relative ai due interventi sono associate due attività di assistenza tecnica.</span><span class="sxs-lookup"><span data-stu-id="2a7c4-160">The service agreement lines for the two jobs have two service tasks attached to them.</span></span> <span data-ttu-id="2a7c4-161">Le attività di assistenza tecnica determinano le transazioni appartenenti a ciascun intervento.</span><span class="sxs-lookup"><span data-stu-id="2a7c4-161">The service tasks determine the transactions that belong to each job.</span></span> <span data-ttu-id="2a7c4-162">Nel primo caso, con l'attività di assistenza tecnica I/C - GB1234 vengono identificate tutte le righe del contratto di assistenza interessate dal controllo e dalla pulizia dell'oggetto GB-1234.</span><span class="sxs-lookup"><span data-stu-id="2a7c4-162">In the first case, service task I/C - GB1234 identifies all the service agreement lines that are involved in the inspection and cleaning of object GB-1234.</span></span> <span data-ttu-id="2a7c4-163">Nel secondo caso, con l'attività di assistenza tecnica RR - GB1234 vengono identificate tutte le righe del contratto di assistenza interessate dall'esecuzione di un intervento di sostituzione di routine.</span><span class="sxs-lookup"><span data-stu-id="2a7c4-163">In the second case, service task RR - GB1234 identifies all the service agreement lines that are involved in completing a routine replacement job.</span></span>

<span data-ttu-id="2a7c4-164">Le relazioni che collegano le attività di assistenza tecnica al contratto specifico sono le seguenti.</span><span class="sxs-lookup"><span data-stu-id="2a7c4-164">The service task relations that connect the service tasks to the specific agreement are as follows:</span></span>

### <a name="service-tasks"></a><span data-ttu-id="2a7c4-165">Attività di assistenza tecnica</span><span class="sxs-lookup"><span data-stu-id="2a7c4-165">Service tasks</span></span>

| <span data-ttu-id="2a7c4-166">Attività di assistenza tecnica</span><span class="sxs-lookup"><span data-stu-id="2a7c4-166">Service task</span></span> | <span data-ttu-id="2a7c4-167">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a7c4-167">Description</span></span>                             | <span data-ttu-id="2a7c4-168">Nota interna</span><span class="sxs-lookup"><span data-stu-id="2a7c4-168">Internal note</span></span>                                                                                                                 | <span data-ttu-id="2a7c4-169">Nota esterna</span><span class="sxs-lookup"><span data-stu-id="2a7c4-169">External note</span></span>                 |
|--------------|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|-------------------------------|
| <span data-ttu-id="2a7c4-170">I/C - GB1234</span><span class="sxs-lookup"><span data-stu-id="2a7c4-170">I/C - GB1234</span></span> | <span data-ttu-id="2a7c4-171">Controllo della scatola ingranaggi GB-1234</span><span class="sxs-lookup"><span data-stu-id="2a7c4-171">Inspection of gearbox GB-1234</span></span>           | <span data-ttu-id="2a7c4-172">Controllo visivo e meccanico e pulizia della scatola ingranaggi GB-1234.</span><span class="sxs-lookup"><span data-stu-id="2a7c4-172">Visual and mechanical inspection and cleaning of gearbox GB-1234</span></span>                                                              | <span data-ttu-id="2a7c4-173">Controllo di routine della scatola ingranaggi</span><span class="sxs-lookup"><span data-stu-id="2a7c4-173">Routine inspection of gearbox</span></span> |
| <span data-ttu-id="2a7c4-174">RR - GB1234</span><span class="sxs-lookup"><span data-stu-id="2a7c4-174">RR - GB1234</span></span>  | <span data-ttu-id="2a7c4-175">Sostituzione di routine di alcuni componenti della scatola ingranaggi GB-1234</span><span class="sxs-lookup"><span data-stu-id="2a7c4-175">Routine replacement of parts in GB-1234</span></span> | <span data-ttu-id="2a7c4-176">Sostituzione di routine dei componenti GR-1 e GR-5 (per le scatole ingranaggi prodotte prima del 2002, sostituzione anche del componente GR-2)</span><span class="sxs-lookup"><span data-stu-id="2a7c4-176">Routine service replacement of GR-1 and GR-5 components (for gearboxes manufactured before 2002, also replace GR-2 component)</span></span> | <span data-ttu-id="2a7c4-177">Sostituzione di routine di alcuni componenti</span><span class="sxs-lookup"><span data-stu-id="2a7c4-177">Routine replacement of parts</span></span>  |

## <a name="group-service-orders"></a><span data-ttu-id="2a7c4-178">Raggruppare ordini di assistenza</span><span class="sxs-lookup"><span data-stu-id="2a7c4-178">Group service orders</span></span>

<span data-ttu-id="2a7c4-179">Quando si creano automaticamente ordini di assistenza, è possibile utilizzare le attività di assistenza tecnica come criteri per il raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="2a7c4-179">When you create service orders automatically, you can use service tasks as grouping criteria.</span></span> <span data-ttu-id="2a7c4-180">Per poter raggruppare gli ordini di assistenza in base a tali attività, è necessario definire nel contratto di assistenza che gli ordini di assistenza basati sul contratto dovranno essere raggruppati in base all'ID dell'attività di assistenza tecnica come criteri di raggruppamento iniziale.</span><span class="sxs-lookup"><span data-stu-id="2a7c4-180">To group service orders by service tasks, define on the service agreement that service orders that are based on the service agreement should be grouped by service task ID as their initial grouping criteria.</span></span>

<span data-ttu-id="2a7c4-181">**Effettuare il raggruppamento in base all'attività di assistenza tecnica**</span><span class="sxs-lookup"><span data-stu-id="2a7c4-181">**Group by service task**</span></span>

1. <span data-ttu-id="2a7c4-182">Fare clic su **Gestione assistenza** \> **Comune** \> **Contratti di assistenza** \> **Contratti di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="2a7c4-182">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>
2. <span data-ttu-id="2a7c4-183">Nella scheda **Impostazione** selezionare **In base all'attività di assistenza** nel campo **Combina ordini di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="2a7c4-183">On the **Setup** tab, select **By service task** in the **Combine service orders** field.</span></span>



