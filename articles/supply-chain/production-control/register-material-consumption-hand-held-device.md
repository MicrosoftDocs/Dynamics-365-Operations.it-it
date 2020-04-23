---
title: Registrare il consumo dei materiali usando un dispositivo mobile
description: In questo argomento viene descritto un flusso di lavoro che consente la registrazione del consumo di materie prime nella produzione tramite un dispositivo portatile.
author: johanhoffmann
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 1706093
ms.assetid: 75ee68e0-4b9f-4f4d-b286-f498e0eb73fa
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 67fbb8eebb637a96638c574373441213c66e9ddc
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3211263"
---
# <a name="register-material-consumption-using-a-mobile-device"></a><span data-ttu-id="26e48-103">Registrare il consumo dei materiali usando un dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="26e48-103">Register material consumption using a mobile device</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="26e48-104">In questo argomento viene descritto un flusso di lavoro che consente la registrazione del consumo di materie prime nella produzione tramite un dispositivo portatile.</span><span class="sxs-lookup"><span data-stu-id="26e48-104">This topic describes a workflow that enables registration of raw material consumption in production by using a handheld device.</span></span>

<a name="introduction"></a><span data-ttu-id="26e48-105">Introduzione</span><span class="sxs-lookup"><span data-stu-id="26e48-105">Introduction</span></span>
------------

<span data-ttu-id="26e48-106">Questo flusso di lavoro è rilevante in presenza di in requisito vincolate per la tracciabilità de materiale.</span><span class="sxs-lookup"><span data-stu-id="26e48-106">This workflow is relevant if there is a strict requirement for material traceability.</span></span> <span data-ttu-id="26e48-107">In questi casi, per gestire la tracciabilità dei materiali, l'ora e la quantità esatti devono essere dichiarati per il consumo.</span><span class="sxs-lookup"><span data-stu-id="26e48-107">In those cases, to maintain traceability of the materials, the exact time and quantity must be reported for the consumption.</span></span> <span data-ttu-id="26e48-108">Questo processo è l'opposto delle operazioni di pre o backflush, in cui è presente uno scostamento tra l'ora di registrazione e l'ora in cui ha luogo il consumo effettivo.</span><span class="sxs-lookup"><span data-stu-id="26e48-108">This process can be seen as opposed to pre- or back-flushing operations, where there is an offset between the time of registration and the time when the actual consumption takes place.</span></span> <span data-ttu-id="26e48-109">Questo spiega perché una strategia di consumo automatico non può essere utilizzata per alcuni materiali con requisiti di tracciabilità.</span><span class="sxs-lookup"><span data-stu-id="26e48-109">This explains why a strategy of automatic consumption cannot be used for some materials with traceability requirements.</span></span> <span data-ttu-id="26e48-110">Esaminiamo uno scenario semplice che spiega come configurare un flusso di lavoro per consentire la registrazione del consumo di materie prime nella produzione tramite un dispositivo portatile.</span><span class="sxs-lookup"><span data-stu-id="26e48-110">Let’s look at a simple scenario that explains how to set up a workflow to enable registration of raw material consumption in production by using a handheld device.</span></span> <span data-ttu-id="26e48-111">[![Configurare un flusso di lavoro per consentire la registrazione del consumo di materie prime tramite un dispositivo portatile](./media/scenario3.png)](./media/scenario3.png)</span><span class="sxs-lookup"><span data-stu-id="26e48-111">[![set up a workflow to enable registration of raw material consumption by using a handheld device](./media/scenario3.png)](./media/scenario3.png)</span></span>

### <a name="scenario-details"></a><span data-ttu-id="26e48-112">Dettagli dello scenario</span><span class="sxs-lookup"><span data-stu-id="26e48-112">Scenario details</span></span>

<span data-ttu-id="26e48-113">Un processo di produzione continua (5) utilizza la materia prima RM-100 controllata per lotto.</span><span class="sxs-lookup"><span data-stu-id="26e48-113">A continuous production process (5) consumes the batch-controlled raw material RM-100.</span></span> <span data-ttu-id="26e48-114">Il materiale è disponibile nell'ubicazione Bulk-001 (1) sulla targa PL -1 con due lotti, B1 e B2, entrambi con una quantità di 100 chilogrammi.</span><span class="sxs-lookup"><span data-stu-id="26e48-114">The material is on-hand on location Bulk-001 (1) on license plate PL-1 with two batches, B1 and B2, both with a quantity of 100 lbs.</span></span> <span data-ttu-id="26e48-115">Il lavoro di magazzino (2) viene emesso e elaborato per RM-100 e il materiale viene prelevato da Bulk-001 presso l'ubicazione di entrata produzione PIL-01 (3), definita come controllato senza targa.</span><span class="sxs-lookup"><span data-stu-id="26e48-115">Warehouse work (2) is released and processed for RM-100, and the material is picked from Bulk-001 to the production input location PIL-01 (3), which is defined as non-license plate controlled.</span></span> <span data-ttu-id="26e48-116">L'operatore pesa il materiale rispetto al materiale dell'ubicazione di entrata produzione (3) e registra il peso e il numero di lotto come consumato (4).</span><span class="sxs-lookup"><span data-stu-id="26e48-116">The machine operator weighs out material from the production input location (3) and registers the weight and batch number as consumed (4).</span></span> <span data-ttu-id="26e48-117">Dall'ubicazione di entrata produzione, parte del materiale viene aggiunta manualmente al processo di produzione in intervalli di tempo definiti.</span><span class="sxs-lookup"><span data-stu-id="26e48-117">From the production input location, a portion of the material is manually added to the production process in defined time intervals.</span></span> <span data-ttu-id="26e48-118">Quando l'operatore aggiunge il materiale, viene pesato su una scala e il numero di lotto viene registrato.</span><span class="sxs-lookup"><span data-stu-id="26e48-118">When the machine operator adds material, it is weighed on a scale and the batch number is registered.</span></span>

## <a name="set-up-theworkflow-to-register-consumption-using-a-handheld-device"></a><span data-ttu-id="26e48-119">Configurare il flusso di lavoro per registrare il consumo utilizzando un dispositivo portatile</span><span class="sxs-lookup"><span data-stu-id="26e48-119">Set up the workflow to register consumption using a handheld device</span></span>
<span data-ttu-id="26e48-120">Creare un prodotto finito, FG-100, con una distinta base che include la materia prima controllata per lotto RM-100.</span><span class="sxs-lookup"><span data-stu-id="26e48-120">Create a finished-good product, FG-100, with a bill of material that has the batch-controlled raw material RM-100.</span></span> <span data-ttu-id="26e48-121">Aggiungere due lotti, B1 e B2, di RM-100 in una quantità pari a 100 nell'ubicazione: Bulk-001 su targa: PL-1.</span><span class="sxs-lookup"><span data-stu-id="26e48-121">Add two batches, B1 and B2, of RM-100 in a quantity of 100 to location: Bulk-001 on license plate: PL-1.</span></span> <span data-ttu-id="26e48-122">Il principio di registrazione del consumo di materiali in entrata sulla riga distinta base per RM-100 è impostato su **Manuale**.</span><span class="sxs-lookup"><span data-stu-id="26e48-122">The flushing principle on the bill of material line for RM-100 is set to **Manual**.</span></span> <span data-ttu-id="26e48-123">Impostare l'ubicazione entrata produzione su PIL-01.</span><span class="sxs-lookup"><span data-stu-id="26e48-123">Set  the production input location to PIL-01.</span></span> <span data-ttu-id="26e48-124">È possibile farlo selezionando questa ubicazione come ubicazione di entrata produzione predefinita nel magazzino 51.</span><span class="sxs-lookup"><span data-stu-id="26e48-124">You can do that by selecting this location as the default production input location on warehouse 51.</span></span>

1.  <span data-ttu-id="26e48-125">Creare una nuova voce di menu per dispositivo mobile:</span><span class="sxs-lookup"><span data-stu-id="26e48-125">Create a new mobile device menu item:</span></span> 

-    <span data-ttu-id="26e48-126">**Nome voce di menu** - Registra consumo materiali.</span><span class="sxs-lookup"><span data-stu-id="26e48-126">**Menu item name** - Register material consumption.</span></span> 
-    <span data-ttu-id="26e48-127">**Titolo** - Registra consumo materiali.</span><span class="sxs-lookup"><span data-stu-id="26e48-127">**Title** - Register material consumption.</span></span> 
-    <span data-ttu-id="26e48-128">**Modalità** - Indiretta.</span><span class="sxs-lookup"><span data-stu-id="26e48-128">**Mode** - Indirect.</span></span> 
-    <span data-ttu-id="26e48-129">**Codice attività** - Registra consumo materiali.</span><span class="sxs-lookup"><span data-stu-id="26e48-129">**Activity code** - Register material consumption.</span></span>

2.  <span data-ttu-id="26e48-130">Aggiungere la voce di menu al menu per dispositivo mobile **Produzione mobile**.</span><span class="sxs-lookup"><span data-stu-id="26e48-130">Add the menu item to the **Production Mobile** device menu.</span></span>
3.  <span data-ttu-id="26e48-131">Creare un ordine di produzione per il prodotto finito:</span><span class="sxs-lookup"><span data-stu-id="26e48-131">Create a production order for the finished product:</span></span> 

-    <span data-ttu-id="26e48-132">**Numero articolo** - FG-100</span><span class="sxs-lookup"><span data-stu-id="26e48-132">**Item number** - FG-100</span></span> 
-    <span data-ttu-id="26e48-133">**Sito** - 5</span><span class="sxs-lookup"><span data-stu-id="26e48-133">**Site** - 5</span></span> 
-    <span data-ttu-id="26e48-134">**Magazzino** - 51</span><span class="sxs-lookup"><span data-stu-id="26e48-134">**Warehouse** - 51</span></span> 
-    <span data-ttu-id="26e48-135">**Quantità** - 150</span><span class="sxs-lookup"><span data-stu-id="26e48-135">**Quantity** - 150</span></span>

<span data-ttu-id="26e48-136">L'ordine di produzione è **Stimato** e **Rilasciato** e il lavoro di magazzino viene creato.</span><span class="sxs-lookup"><span data-stu-id="26e48-136">The production order is **Estimated** and **Released** and warehouse work is created.</span></span>

4.  <span data-ttu-id="26e48-137">Completare il lavoro tramite il flusso di lavoro per il prelievo di materie prime per il dispositivo portatile.</span><span class="sxs-lookup"><span data-stu-id="26e48-137">Complete the work using the workflow for raw material picking for the handheld device.</span></span>

<span data-ttu-id="26e48-138">Questo porterà il materiale dall'ubicazione di stoccaggio all'ubicazione di entrata produzione PIL-01.</span><span class="sxs-lookup"><span data-stu-id="26e48-138">This will bring the material from the bulk location to the production input location PIL-01.</span></span> <span data-ttu-id="26e48-139">Dopo che il lavoro è stato completato, il materiale avrà lo stato **Prelevato nell'ubicazione di entrata produzione**.</span><span class="sxs-lookup"><span data-stu-id="26e48-139">After the work is completed, the material has the status **Picked on the production input location**.</span></span> <span data-ttu-id="26e48-140">Lo stato dopo che il lavoro è stato elaborato può essere **Prelevato** o **Fisico prenotato**.</span><span class="sxs-lookup"><span data-stu-id="26e48-140">The status after work has been processed can be either **Picked** or **Reserved physical**.</span></span> <span data-ttu-id="26e48-141">Ciò viene configurata con il parametro **Stato di emissione dopo aggiunto al modulo di magazzino**.</span><span class="sxs-lookup"><span data-stu-id="26e48-141">This is configured with the parameter **Issue status after put on the warehouse form**.</span></span>

5.  <span data-ttu-id="26e48-142">Avviare l'ordine di produzione dal client o da dispositivo portatile utilizzando la voce di menu **Inizio di produzione**.</span><span class="sxs-lookup"><span data-stu-id="26e48-142">Start the production order either from the client or from the handheld device by using the **Production start** menu item.</span></span>

<span data-ttu-id="26e48-143">Dopo che l'ordine di produzione è stato avviato, è possibile registrare il consumo di materiali con il flusso di lavoro per un dispositivo portatile.</span><span class="sxs-lookup"><span data-stu-id="26e48-143">After the production order has been started, you can register material consumption with the workflow for the handheld device.</span></span> <span data-ttu-id="26e48-144">Iniziamo la registrazione di un consumo di 25 chilogrammi del lotto B1.</span><span class="sxs-lookup"><span data-stu-id="26e48-144">Let's start by registering consumption of 25 lbs of batch B1.</span></span>

6.  <span data-ttu-id="26e48-145">Selezionare la voce di menu **Registra materiale** **consumo** dal menu per il dispositivo portatile, immettere i seguenti dati:</span><span class="sxs-lookup"><span data-stu-id="26e48-145">Select the **Register material** **consumption** menu item in the menu for the hand held device, enter the following details:</span></span> 

-    <span data-ttu-id="26e48-146">Numero dell'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="26e48-146">The production order number.</span></span> 
-    <span data-ttu-id="26e48-147">Ubicazione in cui il materiale dovrà essere consumato, in questo caso PIL-01.</span><span class="sxs-lookup"><span data-stu-id="26e48-147">The location on which the material is going to be consumed, in this case PIL-01.</span></span> 
-    <span data-ttu-id="26e48-148">Numero articolo RM-100.</span><span class="sxs-lookup"><span data-stu-id="26e48-148">Item number RM-100.</span></span> 
-    <span data-ttu-id="26e48-149">Numero lotto B1.</span><span class="sxs-lookup"><span data-stu-id="26e48-149">Batch number B1.</span></span> 
-    <span data-ttu-id="26e48-150">Quantità di 25.</span><span class="sxs-lookup"><span data-stu-id="26e48-150">A quantity of 25.</span></span>

7.  <span data-ttu-id="26e48-151">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="26e48-151">Select **OK**.</span></span>

<span data-ttu-id="26e48-152">Si noti che viene visualizzato sullo schermo il messaggio "Riga giornale di registrazione creata".</span><span class="sxs-lookup"><span data-stu-id="26e48-152">Note that the message "Journal line is created" appears on the display.</span></span> <span data-ttu-id="26e48-153">Nell'ordine di produzione è presente giornale di registrazione aperto di tipo **Distinta di prelievo produzione** per il numero di articolo RM-100 e il numero di lotto B1.</span><span class="sxs-lookup"><span data-stu-id="26e48-153">On the production order there is an open journal of the type **Production picking list** for item number RM-100 and batch number B1.</span></span> 

<span data-ttu-id="26e48-154">È ora possibile scegliere di continuare la registrazione, ad esempio sul numero lotto B2, e ogni volta che si seleziona **OK,** una nuova riga del giornale di registrazione viene aggiunta al giornale di registrazione aperto.</span><span class="sxs-lookup"><span data-stu-id="26e48-154">You can now choose to continue your registration, for example on batch number B2, and each time you select **OK,** a new journal line is added to the open journal.</span></span> 

<span data-ttu-id="26e48-155">Al termine della registrazione, selezionare **Fatto** per registrare il giornale e terminare il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="26e48-155">After you have finished your registration, select **Done** to post the journal and end the workflow.</span></span>

### <a name="additional-comments"></a><span data-ttu-id="26e48-156">Commenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="26e48-156">Additional comments</span></span> 

-   <span data-ttu-id="26e48-157">Se un utente annulla il flusso di lavoro dopo la creazione di una riga del giornale di registrazione, il giornale di registrazione è nello stato non registrato ma se l'utente in un momento successivo utilizza il flusso di lavoro per lo stesso ordine di produzione, le righe verranno aggiunte al giornale di registrazione aperto anziché in un nuovo giornale.</span><span class="sxs-lookup"><span data-stu-id="26e48-157">If a user cancels the workflow after a journal line is created, the journal is in an unposted state but if the user at a later point uses the workflow for the same production order, then the lines will be added to the open journal rather than to a new journal.</span></span>
-   <span data-ttu-id="26e48-158">Il nuovo flusso di lavoro supporta anche la registrazione dei numeri di serie.</span><span class="sxs-lookup"><span data-stu-id="26e48-158">The new workflow also supports the registration of serial numbers.</span></span>
-   <span data-ttu-id="26e48-159">È possibile registrare solo un numero di articolo definito nella distinta base o nella formula per l'ordine di produzione o l'ordine lotto selezionato.</span><span class="sxs-lookup"><span data-stu-id="26e48-159">It is only possible to register an item number that is defined in the bill of material or in the formula for the selected production order or batch order.</span></span>
-   <span data-ttu-id="26e48-160">Il materiale può essere consumato in quantità eccessiva.</span><span class="sxs-lookup"><span data-stu-id="26e48-160">Material can be overconsumed.</span></span> <span data-ttu-id="26e48-161">Ad esempio, se si stima una quantità consumata di materiale pari a 100 kg, è possibile che si verifichi un consumo eccessivo pari a una quantità, ad esempio, di 105 chilogrammi.</span><span class="sxs-lookup"><span data-stu-id="26e48-161">For example, if the material is estimated to be consumed with the quantity of 100 lbs, then it can be overconsumed with a quantity of, for example, 105 lbs.</span></span>


