---
title: Ordini di lavoro creati manualmente
description: In questo argomento viene descritto come creare manualmente ordini di lavoro in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 80593ddaaa5f327513781dbdd4e3163de4212ced
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208111"
---
# <a name="manually-created-work-orders"></a><span data-ttu-id="6aecd-103">Ordini di lavoro creati manualmente</span><span class="sxs-lookup"><span data-stu-id="6aecd-103">Manually created work orders</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="6aecd-104">È possibile creare ordini di lavoro manualmente in due modi:</span><span class="sxs-lookup"><span data-stu-id="6aecd-104">You can create work orders manually in two ways:</span></span>

- <span data-ttu-id="6aecd-105">Nella pagina **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**</span><span class="sxs-lookup"><span data-stu-id="6aecd-105">On the **All work orders** or **Active work orders** page</span></span> 
- <span data-ttu-id="6aecd-106">Nella pagina **Tutte le richieste di intervento di manutenzione** o **Richieste di intervento di manutenzione attive** o **Richieste di intervento di manutenzione delle unità funzionali personali**</span><span class="sxs-lookup"><span data-stu-id="6aecd-106">On the **All maintenance requests** or **Active maintenance requests** or **My functional location maintenance requests** page</span></span> 

## <a name="create-work-order"></a><span data-ttu-id="6aecd-107">Crea ordine di lavoro</span><span class="sxs-lookup"><span data-stu-id="6aecd-107">Create work order</span></span>

1. <span data-ttu-id="6aecd-108">Selezionare **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.</span><span class="sxs-lookup"><span data-stu-id="6aecd-108">Selece **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="6aecd-109">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="6aecd-109">Select **New**.</span></span>

3. <span data-ttu-id="6aecd-110">Nella finestra di dialogo **Crea ordine di lavoro**, selezionare un tipo di ordine di lavoro nel campo **Tipo di ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="6aecd-110">In the **Create work order** dialog, select a work order type in the **Work order type** field.</span></span>

4. <span data-ttu-id="6aecd-111">Se necessario, selezionare una **descrizione**.</span><span class="sxs-lookup"><span data-stu-id="6aecd-111">If required, select a **Description**.</span></span>

5. <span data-ttu-id="6aecd-112">Selezionare il cespite nel campo **Cespite**.</span><span class="sxs-lookup"><span data-stu-id="6aecd-112">In the **Asset** field, select the asset.</span></span>

>[!NOTE]
><span data-ttu-id="6aecd-113">Quando si seleziona un cespite, tre schede potrebbero essere disponibili nel menu a discesa **Cespite**:</span><span class="sxs-lookup"><span data-stu-id="6aecd-113">When you select an asset, three tabs might be available in the **Asset** drop-down:</span></span> 

- <span data-ttu-id="6aecd-114">**Cespiti attivi** - Questa scheda include un elenco di tutti i cespiti con stato del ciclo di vita del cespite "Attivo".</span><span class="sxs-lookup"><span data-stu-id="6aecd-114">**Active assets** - This tab contains a list of all assets that have an "Active" asset lifecycle state.</span></span> 
- <span data-ttu-id="6aecd-115">**Visualizzazione cespiti** - Questa scheda mostra una visualizzazione ad albero delle unità funzionali e dei cespiti installati nelle unità.</span><span class="sxs-lookup"><span data-stu-id="6aecd-115">**Asset view** - This tab displays a tree view of functional locations and the assets installed on them.</span></span>
- <span data-ttu-id="6aecd-116">**Cespiti personali** - Questa scheda include i cespiti correlati alle unità funzionali che possono essere allocate al lavoratore che esegue l'accesso a sistema.</span><span class="sxs-lookup"><span data-stu-id="6aecd-116">**My assets** - This tab contains assets that are related to the functional locations that you (the worker who is signed in to the system) may be allocated to.</span></span> <span data-ttu-id="6aecd-117">Per informazioni sull'impostazione, vedere [Addetti alla manutenzione e gruppi di lavoratori](../setup-for-objects/workers-and-worker-groups.md). Se le unità funzionali non sono impostate per un lavoratore in [Addetti alla manutenzione e gruppi di lavoratori](../setup-for-objects/workers-and-worker-groups.md), la scheda **Cespiti personali** non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="6aecd-117">(For information about the setup, see [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).) If no functional locations are set up on a worker in [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md), the **My assets** tab isn't available.</span></span> 

6. <span data-ttu-id="6aecd-118">Selezionare il tipo di processo di manutenzione per l'ordine di lavoro nel campo **Tipo di processo di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="6aecd-118">In the **Maintenance job type** field, select a maintenance job type for the work order.</span></span>

7. <span data-ttu-id="6aecd-119">Se necessario, selezionare **Variante tipi di processo di manutenzione** e **Settore**.</span><span class="sxs-lookup"><span data-stu-id="6aecd-119">If required, select **Maintenance job type variant** and **Trade**.</span></span>

8. <span data-ttu-id="6aecd-120">Se necessario, è possibile modificare il livello di servizio di ordine di lavoro nel campo **Livello servizio**.</span><span class="sxs-lookup"><span data-stu-id="6aecd-120">If required, you can change the work order service level in the **Service level** field.</span></span>

9. <span data-ttu-id="6aecd-121">Selezionare le **date di inizio** e **di fine previste** nei campi correlati.</span><span class="sxs-lookup"><span data-stu-id="6aecd-121">Select **Expected start** and **Expected end** dates in the related fields.</span></span>

10. <span data-ttu-id="6aecd-122">Fare clic su **OK** per creare l'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6aecd-122">Click **OK** to create the work order.</span></span>

11. <span data-ttu-id="6aecd-123">Nella pagina elenco **Tutti gli ordini di lavoro**, è possibile modificare l'ordine di lavoro secondo le necessità.</span><span class="sxs-lookup"><span data-stu-id="6aecd-123">On the **All work orders** list page, you can edit the work order as you require.</span></span>

<span data-ttu-id="6aecd-124">Notare i punti seguenti:</span><span class="sxs-lookup"><span data-stu-id="6aecd-124">Note the following points:</span></span>

- <span data-ttu-id="6aecd-125">Nella visualizzazione dettagli della pagina elenco **Tutti gli ordini di lavoro**, è possibile aggiungere vari cespiti a un ordine di lavoro aggiungendo righe nella Scheda dettaglio **Processi di manutenzione ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="6aecd-125">In the details view on the **All work orders** list page, you can add several assets to a work order by adding lines on the **Work order maintenance jobs** FastTab.</span></span> <span data-ttu-id="6aecd-126">In un cespite, è possibile selezionare solo i tipi di processo di manutenzione definiti nel tipo di cespite selezionato per il cespite.</span><span class="sxs-lookup"><span data-stu-id="6aecd-126">On an asset, you can select only the maintenance job types that are defined on the asset type that is selected on the asset.</span></span>  

- <span data-ttu-id="6aecd-127">Se si modifica un livello di servizio cespiti o una criticità cespiti dopo che è stato già utilizzato il cespite in un ordine di lavoro, il livello di servizio o la criticità nell'ordine di lavoro non viene aggiornato di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="6aecd-127">If you change an asset service level or an asset criticality after you've used the asset on a work order, the service level or criticality on the work order isn't updated accordingly.</span></span> <span data-ttu-id="6aecd-128">Per ulteriori informazioni sui livelli di servizio e le criticità, vedere [Livello del servizio cespiti](../setup-for-objects/object-priorities.md) e [Tipi di criticità dei cespiti](../setup-for-objects/object-criticalities.md).</span><span class="sxs-lookup"><span data-stu-id="6aecd-128">For more information about service levels and criticalities, see [Asset service levels](../setup-for-objects/object-priorities.md) and [Asset criticality types](../setup-for-objects/object-criticalities.md).</span></span>

- <span data-ttu-id="6aecd-129">La criticità in un ordine di lavoro viene ricalcolata ogni volta in cui un processo ordine di lavoro viene aggiunto o eliminato dall'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6aecd-129">Criticality on a work order is recalculated every time a work order job is added to or deleted from the work order.</span></span>

- <span data-ttu-id="6aecd-130">Nella visualizzazione dettagli **Tutti gli ordini di lavoro** > scheda **Intestazione** > Scheda dettaglio **Programma**, è possibile selezionare un gruppo di addetti alla manutenzione responsabile o un addetto alla manutenzione responsabile nei campi **Gruppo responsabile** o **Responsabile**.</span><span class="sxs-lookup"><span data-stu-id="6aecd-130">In the **All work orders** details view > **Header** tab > **Schedule** FastTab, in the **Responsible group** or **Responsible** field, you can select a responsible maintenance worker group or a responsible maintenance worker.</span></span> <span data-ttu-id="6aecd-131">Queste impostazioni possono essere modificate quando l'ordine di lavoro è attivo.</span><span class="sxs-lookup"><span data-stu-id="6aecd-131">These settings can be changed while the work order is active.</span></span> <span data-ttu-id="6aecd-132">Ad esempio, possono essere modificate quando cambia lo stato del ciclo di vita dell'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6aecd-132">For example, they can be changed when the work order lifecycle state changes.</span></span> <span data-ttu-id="6aecd-133">La selezione automatica effettuata durante la creazione di ordini di lavoro è basata sull'impostazione nella pagina **Addetti alla manutenzione responsabili**.</span><span class="sxs-lookup"><span data-stu-id="6aecd-133">The automatic selection that is made during work order creation is based on the setup on the **Responsible maintenance workers** page.</span></span> <span data-ttu-id="6aecd-134">Se si aggiungono o rimuovono i processi di ordine di lavoro dopo aver creato un ordine di lavoro e se i campi **Gruppo responsabile** e **Responsabile** sono vuoti quando si aggiorna un ordine di lavoro, Gestione cespiti cerca una possibile corrispondenza nella pagina di impostazione per un addetto alla manutenzione responsabile o un gruppo di addetti alla manutenzione responsabile.</span><span class="sxs-lookup"><span data-stu-id="6aecd-134">If you add or remove work order jobs after you've created a work order, and if the **Responsible group** and **Responsible** fields are blank when you update the work order, Asset Management tries to find a responsible maintenance worker group or a responsible maintenance worker for a possible match on the setup page.</span></span> <span data-ttu-id="6aecd-135">Il campo **Gruppo responsabile** o **Responsabile** è già impostato quando si aggiorna l'ordine di lavoro e non viene apportata alcuna modifica.</span><span class="sxs-lookup"><span data-stu-id="6aecd-135">If the **Responsible group** or **Responsible** field is already set when you update the work order, no changes are made.</span></span> <span data-ttu-id="6aecd-136">Per ulteriori informazioni sugli addetti alla manutenzione responsabile e sui gruppi di addetti alla manutenzione responsabile, vedere [Addetti alla manutenzione responsabili](../setup-for-maintenance-requests/responsible-workers.md).</span><span class="sxs-lookup"><span data-stu-id="6aecd-136">For more information about responsible maintenance workers and worker groups, see [Responsible maintenance workers](../setup-for-maintenance-requests/responsible-workers.md).</span></span>

- <span data-ttu-id="6aecd-137">Nella pagina [Stato della manutenzione](../controlling-and-reporting/maintenance-status.md), è possibile eseguire un calcolo per ottenere una panoramica del carico di lavoro relativo agli ordini di lavoro ricevuti e completati.</span><span class="sxs-lookup"><span data-stu-id="6aecd-137">From the [Maintenance status](../controlling-and-reporting/maintenance-status.md) page, you can do a calculation to get an overview of the workload for incoming and completed work orders.</span></span>  

- <span data-ttu-id="6aecd-138">Nella visualizzazione dettagli della pagina **Tutti gli ordini di lavoro**, nella Scheda dettaglio **Dettagli riga**, è possibile utilizzare i campi **Longitudine** e **Latitudine** per aggiungere le coordinate geografiche per il cespite selezionato nel processo ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6aecd-138">In the details view of the **All work orders** page, on the **Line details** FastTab, you can use the **Latitude** and **Longitude** fields to add geographic coordinates for the asset that is selected on the work order job.</span></span>  


## <a name="create-related-work-order"></a><span data-ttu-id="6aecd-139">Crea ordine di lavoro correlato</span><span class="sxs-lookup"><span data-stu-id="6aecd-139">Create related work order</span></span>

<span data-ttu-id="6aecd-140">È possibile creare un ordine di lavoro basato su un ordine di lavoro esistente.</span><span class="sxs-lookup"><span data-stu-id="6aecd-140">You can create a work order that is related to an existing work order.</span></span> <span data-ttu-id="6aecd-141">Questa funzionalità è utile ad esempio se si desidera utilizzare ordini di lavoro principali e secondari.</span><span class="sxs-lookup"><span data-stu-id="6aecd-141">This capability is useful if, for example, you want to work with primary and secondary work orders.</span></span> <span data-ttu-id="6aecd-142">Un nuovo ordine di lavoro è basato su un processo di ordine di lavoro di un ordine di lavoro esistente.</span><span class="sxs-lookup"><span data-stu-id="6aecd-142">A new work order is based on a work order job from an existing work order.</span></span>

1. <span data-ttu-id="6aecd-143">Selezionare **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.</span><span class="sxs-lookup"><span data-stu-id="6aecd-143">Select **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="6aecd-144">Selezionare l'ordine di lavoro di cui creare un ordine di lavoro correlato.</span><span class="sxs-lookup"><span data-stu-id="6aecd-144">Select the work order to create a related work order for.</span></span>

3. <span data-ttu-id="6aecd-145">Nella scheda **Ordine di lavoro** del riquadro azioni, nel gruppo **Nuovo**, selezionare **Ordine di lavoro correlato**.</span><span class="sxs-lookup"><span data-stu-id="6aecd-145">On the Action Pane, on the **Work order** tab, in the **New** group, select **Related work order**.</span></span>

4. <span data-ttu-id="6aecd-146">Nella finestra di dialogo **Creare ordine di lavoro correlato**, selezionare il processo di ordine di lavoro per il quale si desidera creare un ordine di lavoro correlato nel campo **Processo ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="6aecd-146">In the **Create related work order** dialog, in the **Work order job** field, select the work order job to create a related work order for.</span></span>

5. <span data-ttu-id="6aecd-147">Selezionare il tipo di processo di manutenzione nel campo **Tipo di processo di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="6aecd-147">Select a maintenance job type in the **Maintenance job type** field.</span></span>

6. <span data-ttu-id="6aecd-148">Selezionare la variante e il settore associato al tipo di processo di manutenzione nei campi **Variante tipi di processo di manutenzione** e **Settore**.</span><span class="sxs-lookup"><span data-stu-id="6aecd-148">Select a related maintenance job type variant and trade in the **Maintenance job type variant** and **Trade** fields, as you require.</span></span>

7. <span data-ttu-id="6aecd-149">Se l'ordine di lavoro è il primo ordine di lavoro correlato creato per l'ordine di lavoro selezionato, effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="6aecd-149">If this work order is the first related work order that has been created for the selected work order, follow these steps:</span></span>
    1. <span data-ttu-id="6aecd-150">Selezionare l'opzione **Nuovo ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="6aecd-150">Select the **New work order** option.</span></span>
    2. <span data-ttu-id="6aecd-151">Nel campo **Tipo di ordine di lavoro** selezionare un tipo di ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6aecd-151">In  the **Work order type** field, select a work order type.</span></span>
    3. <span data-ttu-id="6aecd-152">Nel campo **Descrizione** immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="6aecd-152">In the **Description**, enter a description.</span></span>
    4. <span data-ttu-id="6aecd-153">Modificare il livello di servizio di ordine di lavoro nel campo **Livello servizio** secondo le necessità.</span><span class="sxs-lookup"><span data-stu-id="6aecd-153">In the **Service level** field, change the work order service level as you require.</span></span>
    5. <span data-ttu-id="6aecd-154">Nei campi **Data di inizio prevista** e **Data di fine prevista**, selezionare le date di inizio e fine previste.</span><span class="sxs-lookup"><span data-stu-id="6aecd-154">In the **Expected start** and **Expected end** fields, select the expected start and end dates.</span></span>
    6. <span data-ttu-id="6aecd-155">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6aecd-155">Select **OK**.</span></span> <span data-ttu-id="6aecd-156">Il nuovo ordine di lavoro correlato è visualizzato nella pagina elenco **Tutti gli ordini di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="6aecd-156">The new related work order is shown on the **All work orders** list page.</span></span>  

8. <span data-ttu-id="6aecd-157">Se l'ordine di lavoro per cui si sta creando questo ordine di lavoro correlato ha già ordini di lavoro correlati, attenersi alla seguente procedura per aggiungere un nuovo processo di ordine di lavoro a un ordine di lavoro correlato esistente:</span><span class="sxs-lookup"><span data-stu-id="6aecd-157">If the work order that you're creating this related work order for already has related work orders, follow these steps to add a new work order job to an existing related work order:</span></span>
    1. <span data-ttu-id="6aecd-158">Selezionare l'opzione **Aggiungi a ordine di lavoro correlato**.</span><span class="sxs-lookup"><span data-stu-id="6aecd-158">Select the **Add to related work order** option.</span></span>
    2. <span data-ttu-id="6aecd-159">Nel campo **Ordine di lavoro** selezionare l'ordine di lavoro correlato a cui si desidera aggiungere un nuovo processo di ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6aecd-159">In the **Work order** field, select the related work order to add a new work order job to.</span></span>
    3. <span data-ttu-id="6aecd-160">Modificare il livello di servizio di ordine di lavoro nel campo **Livello servizio** secondo le necessità.</span><span class="sxs-lookup"><span data-stu-id="6aecd-160">In the **Service level** field, change the work order service level as you require.</span></span>
    4. <span data-ttu-id="6aecd-161">Nei campi **Data di inizio prevista** e **Data di fine prevista**, modificare le date di inizio e fine previste secondo le necessità.</span><span class="sxs-lookup"><span data-stu-id="6aecd-161">In the **Expected start** and **Expected end** fields, change the expected start and end dates as you require.</span></span>
    5. <span data-ttu-id="6aecd-162">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6aecd-162">Select **OK**.</span></span> <span data-ttu-id="6aecd-163">Il processo di ordine di lavoro viene aggiunto all'ordine di lavoro correlato esistente.</span><span class="sxs-lookup"><span data-stu-id="6aecd-163">The work order job is added to the existing related work order.</span></span>

<span data-ttu-id="6aecd-164">Nella figura seguente è illustrato un esempio della finestra di dialogo **Crea ordine di lavoro correlato**.</span><span class="sxs-lookup"><span data-stu-id="6aecd-164">The illustration below shows an example of the **Create related work order** dialog.</span></span>

![Figura 1](media/03-work-orders.png)

>[!NOTE]
><span data-ttu-id="6aecd-166">Se è stata impostata una maschera di ordine di lavoro correlato in **Parametri di gestione cespiti** > scheda **Ordini di lavoro** > campo **Maschera ordini di lavoro correlati**, gli ID di ordine di lavoro saranno creati in base all'impostazione della maschera.</span><span class="sxs-lookup"><span data-stu-id="6aecd-166">If you've set up a related work order mask in **Asset management parameters** > **Work orders** tab > **Related work order mask** field, work order IDs are created according to the mask setup.</span></span> <span data-ttu-id="6aecd-167">Se non è stata impostata una maschera di ordine di lavoro correlato, per gli ordini di lavoro correlati viene utilizzato l'ID di ordine di lavoro disponibile successivo.</span><span class="sxs-lookup"><span data-stu-id="6aecd-167">If no related work order mask is set up, the next available work order ID is used for related work orders.</span></span>

## <a name="copy-a-work-order"></a><span data-ttu-id="6aecd-168">Copiare un ordine di lavoro</span><span class="sxs-lookup"><span data-stu-id="6aecd-168">Copy a work order</span></span>

<span data-ttu-id="6aecd-169">È possibile creare rapidamente un nuovo ordine di lavoro da un ordine di lavoro esistente.</span><span class="sxs-lookup"><span data-stu-id="6aecd-169">You can quickly create a new work order from an existing work order.</span></span> <span data-ttu-id="6aecd-170">Questo modo di utilizzare gli ordini di lavoro differisce dalla creazione di ordini di lavoro basati sui [piani di manutenzione](../preventive-and-reactive-maintenance/maintenance-plans.md).</span><span class="sxs-lookup"><span data-stu-id="6aecd-170">This way of working with work orders differs from the creation of work orders based on [maintenance plans](../preventive-and-reactive-maintenance/maintenance-plans.md).</span></span> <span data-ttu-id="6aecd-171">È utile se, ad esempio, un ordine di lavoro contiene numerosi processi di ordine di lavoro con vari processi da completare in diversi cespiti a intervalli regolari.</span><span class="sxs-lookup"><span data-stu-id="6aecd-171">It's useful if, for example, a work order contains many work order jobs, and the various jobs should be completed on different assets at regular intervals.</span></span>

1. <span data-ttu-id="6aecd-172">Selezionare **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.</span><span class="sxs-lookup"><span data-stu-id="6aecd-172">Select **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="6aecd-173">Selezionare l'ordine di lavoro da cui copiare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="6aecd-173">Select the work order to copy content from.</span></span>

3. <span data-ttu-id="6aecd-174">Nella scheda **Ordine di lavoro** del riquadro azioni > gruppo **Nuovo**, selezionare **Copia ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="6aecd-174">On the Action Pane > **Work order** tab > **New** group, select **Copy work order**.</span></span>

4. <span data-ttu-id="6aecd-175">Viene visualizzata l'impostazione dell'ordine di lavoro selezionato.</span><span class="sxs-lookup"><span data-stu-id="6aecd-175">The work order setup from the selected work order is shown.</span></span> <span data-ttu-id="6aecd-176">È possibile modificare alcuni campi secondo le necessità.</span><span class="sxs-lookup"><span data-stu-id="6aecd-176">You can edit some of the fields as you require.</span></span>

5. <span data-ttu-id="6aecd-177">Selezionare **OK** per creare il nuovo ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6aecd-177">Select **OK** to create the new work order.</span></span>

6. <span data-ttu-id="6aecd-178">Nella pagina elenco **Tutti gli ordini di lavoro**, è possibile modificare l'ordine di lavoro secondo le necessità.</span><span class="sxs-lookup"><span data-stu-id="6aecd-178">On the **All work orders** list page, you can edit the work order as you require.</span></span>

>[!NOTE]
><span data-ttu-id="6aecd-179">Quando si crea il nuovo ordine di lavoro, alcune informazioni vengono copiate direttamente dall'ordine di lavoro esistente.</span><span class="sxs-lookup"><span data-stu-id="6aecd-179">When the new work order is created, some information is copied directly from the existing work order.</span></span> <span data-ttu-id="6aecd-180">Le informazioni su previsioni, strumenti, liste di controllo di manutenzione, unità funzionale, indirizzi e pianificazione non vengono copiate.</span><span class="sxs-lookup"><span data-stu-id="6aecd-180">Information about forecasts, tools, maintenance checklists, functional location, addresses, and scheduling isn't copied.</span></span> <span data-ttu-id="6aecd-181">Vengono invece inizializzate dall'impostazione corrente in Gestione risorse.</span><span class="sxs-lookup"><span data-stu-id="6aecd-181">Instead, it's initialized from the current setup in Asset Management.</span></span> <span data-ttu-id="6aecd-182">Pertanto, se tali informazioni sono state modificate tra il momento in cui è stato creato il primo ordine di lavoro e il momento in cui è stata effettuata una copia dell'ordine di lavoro, le modifiche sono incluse nel nuovo ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6aecd-182">Therefore, if that information was changed between the time when the first work order was created and the time when you made a copy of the work order, the changes are included in the new work order.</span></span> <span data-ttu-id="6aecd-183">Esempi di questa operazione sono le modifiche alle previsioni e gli aggiornamenti agli elenchi di controllo di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="6aecd-183">Examples include changes to forecasts and updates to maintenance checklists.</span></span>

<span data-ttu-id="6aecd-184">Nella figura seguente è illustrato un esempio della finestra di dialogo **Copia ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="6aecd-184">The illustration below shows an example of the **Copy work order** dialog.</span></span>

![Figura 2](media/04-work-orders.png)


## <a name="create-a-work-order-based-on-a-maintenance-request"></a><span data-ttu-id="6aecd-186">Creare un ordine di lavoro basato su una richiesta di intervento di manutenzione</span><span class="sxs-lookup"><span data-stu-id="6aecd-186">Create a work order based on a maintenance request</span></span>

1. <span data-ttu-id="6aecd-187">Selezionare **Gestione cespiti** > **Comune** > **Richieste di intervento di manutenzione** > **Tutte le richieste di intervento di manutenzione** o **Richieste di intervento di manutenzione attive**.</span><span class="sxs-lookup"><span data-stu-id="6aecd-187">Select **Asset management** > **Common** > **Maintenance requests** > **All maintenance requests** or **Active maintenance requests**.</span></span>

2. <span data-ttu-id="6aecd-188">Selezionare la richiesta di intervento di manutenzione per la quale creare un ordine di lavoro e fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="6aecd-188">Select the maintenance request to create a work order for, and click **Edit**.</span></span>

3. <span data-ttu-id="6aecd-189">Nella scheda **Richiesta di intervento di manutenzione** del riquadro azioni > gruppo **Nuovo**, selezionare **Ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="6aecd-189">On the Action Pane > **Maintenance request** tab > **New** group, select **Work order**.</span></span>

4. <span data-ttu-id="6aecd-190">Nella finestra di dialogo **Ordine di lavoro**, impostare i campi.</span><span class="sxs-lookup"><span data-stu-id="6aecd-190">In the **Work order** dialog, set the fields.</span></span> <span data-ttu-id="6aecd-191">Se un tipo di processo di manutenzione è stato selezionato nella richiesta di intervento di manutenzione, è possibile selezionare un tipo di processo di manutenzione diverso quando si crea l'ordine di lavoro secondo le necessità.</span><span class="sxs-lookup"><span data-stu-id="6aecd-191">If a maintenance job type has been selected in the maintenance request, you can select a different maintenance job type when you create the work order, as you require.</span></span>

5. <span data-ttu-id="6aecd-192">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6aecd-192">Select **OK**.</span></span> <span data-ttu-id="6aecd-193">Il messaggio informa che l'ordine di lavoro è stato creato.</span><span class="sxs-lookup"><span data-stu-id="6aecd-193">A message notifies you that the work order has been created.</span></span>

6. <span data-ttu-id="6aecd-194">Per visualizzare gli ordini di lavoro collegati a una richiesta di intervento di manutenzione, nella pagine elenco **Tutte le richieste di intervento di manutenzione** o **Richieste di intervento di manutenzione attive**, selezionare la richiesta di intervento di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="6aecd-194">To view the work orders that are connected to a maintenance request, on the **All maintenance requests** or **Active maintenance requests** list page, select the maintenance request.</span></span> <span data-ttu-id="6aecd-195">Nella scheda **Richiesta di intervento di manutenzione** del riquadro azioni, nel gruppo **Visualizza**, selezionare **Ordini di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="6aecd-195">Then, on the Action Pane, on the **Maintenance request** tab, in the **View** group, select **Work orders**.</span></span>


<span data-ttu-id="6aecd-196">Nella figura seguente è illustrato un esempio della finestra di dialogo **Creare ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="6aecd-196">The illustration below shows an example of the **Create work order** dialog.</span></span>

![Figura 3](media/05-work-orders.png)


>[!NOTE]
><span data-ttu-id="6aecd-198">Per creare automaticamente gli ordini di lavoro è possibile pianificare i processi del piano di manutenzione o impostare la creazione automatica dei [piani di manutenzione](../preventive-and-reactive-maintenance/maintenance-plans.md) o [cicli di manutenzione](../preventive-and-reactive-maintenance/maintenance-rounds.md) per un cespite.</span><span class="sxs-lookup"><span data-stu-id="6aecd-198">If you want work orders to be created automatically, you can schedule maintenance plan jobs, or you can set up "Auto create" [maintenance plans](../preventive-and-reactive-maintenance/maintenance-plans.md) or [maintenance rounds](../preventive-and-reactive-maintenance/maintenance-rounds.md) on an asset.</span></span> <span data-ttu-id="6aecd-199">Gli ordini di lavoro creati dalle richieste di intervento di manutenzione nella pagina elenco **Tutti i programmi di manutenzione** hanno i tipi di processo di manutenzione selezionati nelle richieste di intervento di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="6aecd-199">Work orders that are created from maintenance requests on the **All maintenance schedule** list page have the maintenance job types that are selected on the maintenance requests.</span></span>

