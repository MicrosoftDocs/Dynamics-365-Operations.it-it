---
title: Ordini di lavoro creati manualmente
description: In questo argomento viene descritto come creare manualmente ordini di lavoro in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 261448a134a7c1aacfbb4ea6f954ce03a63c23e2
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875734"
---
# <a name="manually-created-work-orders"></a><span data-ttu-id="82164-103">Ordini di lavoro creati manualmente</span><span class="sxs-lookup"><span data-stu-id="82164-103">Manually created work orders</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="82164-104">È possibile creare ordini di lavoro manualmente in due modi:</span><span class="sxs-lookup"><span data-stu-id="82164-104">You can create work orders manually in two ways:</span></span>

- <span data-ttu-id="82164-105">In **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**</span><span class="sxs-lookup"><span data-stu-id="82164-105">in **All work orders** or **Active work orders**</span></span>  
- <span data-ttu-id="82164-106">In **Tutte le richieste di intervento di manutenzione** o **Richieste di intervento di manutenzione attive** o **Richieste di intervento di manutenzione delle unità funzionali personali**.</span><span class="sxs-lookup"><span data-stu-id="82164-106">in **All maintenance requests** or **Active maintenance requests** or **My functional location maintenance requests**</span></span>  

## <a name="create-work-order"></a><span data-ttu-id="82164-107">Crea ordine di lavoro</span><span class="sxs-lookup"><span data-stu-id="82164-107">Create work order</span></span>

1. <span data-ttu-id="82164-108">Fare clic su **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.</span><span class="sxs-lookup"><span data-stu-id="82164-108">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="82164-109">Fare clic sul pulsante **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="82164-109">Click the **New** button.</span></span>

3. <span data-ttu-id="82164-110">Nel menu a discesa **Crea ordine di lavoro**, selezionare un tipo di ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="82164-110">In the **Create work order** drop-down, select a work order type.</span></span>

4. <span data-ttu-id="82164-111">Se necessario, selezionare una descrizione.</span><span class="sxs-lookup"><span data-stu-id="82164-111">If required, select a description.</span></span>

5. <span data-ttu-id="82164-112">Selezionare il cespite per l'ordine di lavoro nonché un tipo di processo di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="82164-112">Select the asset for the work order as well as a maintenance job type.</span></span>

>[!NOTE]
><span data-ttu-id="82164-113">Quando si seleziona un cespite, è possibile che siano disponibili tre schede: la scheda **Cespiti personali** include i cespiti correlati alle unità funzionali a cui il lavoratore connesso al sistema può essere assegnato (impostazione in [Addetti e gruppi di addetti alla manutenzione](../setup-for-objects/workers-and-worker-groups.md)).</span><span class="sxs-lookup"><span data-stu-id="82164-113">When you select an asset, three tabs may be available: The **My assets** tab contains assets related to the functional locations to which you (the worker who is logged on the system) may be allocated (set up in [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md)).</span></span> <span data-ttu-id="82164-114">Se non sono impostate unità funzionali per un lavoratore in [Addetti e gruppi di addetti alla manutenzione](../setup-for-objects/workers-and-worker-groups.md), la scheda **Cespiti personali** non sarà visibile.</span><span class="sxs-lookup"><span data-stu-id="82164-114">If no functional locations are set up on a worker in [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md), the **My assets** tab will not be visible.</span></span> <span data-ttu-id="82164-115">La scheda **Cespiti attivi** include un elenco di tutti i cespiti con stato del ciclo di vita del cespite "Attivo".</span><span class="sxs-lookup"><span data-stu-id="82164-115">The **Active assets** tab contains a list of all assets with asset lifecycle state "Active".</span></span> <span data-ttu-id="82164-116">La scheda **Visualizzazione cespiti** mostra una visualizzazione struttura delle unità funzionali e dei cespiti installati nelle unità.</span><span class="sxs-lookup"><span data-stu-id="82164-116">The **Asset view** tab displays a tree view of functional locations and assets installed on those locations.</span></span>

6. <span data-ttu-id="82164-117">Se necessario, selezionare **Variante tipi di processo di manutenzione** e **Settore**.</span><span class="sxs-lookup"><span data-stu-id="82164-117">If required, select **Maintenance job type variant** and **Trade**.</span></span>

7. <span data-ttu-id="82164-118">Se necessario, è possibile modificare il livello di servizio di ordine di lavoro nel campo **Livello servizio**.</span><span class="sxs-lookup"><span data-stu-id="82164-118">If required, you can change the work order service level in the **Service level** field.</span></span>

8. <span data-ttu-id="82164-119">Selezionare le date di inizio e di fine previste nei campi correlati.</span><span class="sxs-lookup"><span data-stu-id="82164-119">Select expected start and end dates in the related fields.</span></span>

9. <span data-ttu-id="82164-120">Fare clic su **OK** per creare un nuovo ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="82164-120">Click **OK** to create a new work order.</span></span>

10. <span data-ttu-id="82164-121">Modificare l'ordine di lavoro in **Tutti gli ordini di lavoro**, se necessario.</span><span class="sxs-lookup"><span data-stu-id="82164-121">Edit the work order in **All work orders**, if required.</span></span>

- <span data-ttu-id="82164-122">In **Tutti gli ordini di lavoro**, è possibile aggiungere vari cespiti a un ordine di lavoro nella visualizzazione dettagli aggiungendo righe nella Scheda dettaglio **Processi di manutenzione ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="82164-122">In **All work orders**, You can add several assets to a work order in Details view by adding lines on the **Work order maintenance jobs** FastTab.</span></span> <span data-ttu-id="82164-123">In un cespite, è possibile selezionare solo i tipi di processo di manutenzione definiti nel tipo di cespite selezionato per il cespite.</span><span class="sxs-lookup"><span data-stu-id="82164-123">On an asset, you can only select the maintenance job types that are defined on the asset type selected for the asset.</span></span>  
- <span data-ttu-id="82164-124">Se si è modificato un livello di servizio cespiti o una criticità cespiti dopo l'utilizzo in un ordine di lavoro (fare riferimento a [Livelli di servizio cespiti](../setup-for-objects/object-priorities.md) e [Criticità cespiti](../setup-for-objects/object-criticalities.md)), il livello di servizio o la criticità nell'ordine di lavoro non verrà aggiornato di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="82164-124">If you have changed an asset service level or an asset criticality after you have used them on a work order (refer to [Asset service levels](../setup-for-objects/object-priorities.md) and [Asset criticalities](../setup-for-objects/object-criticalities.md)), the service level or criticality on the work order is not updated accordingly.</span></span>
- <span data-ttu-id="82164-125">La criticità in un ordine di lavoro viene ricalcolata ogni volta che una riga di ordine di lavoro viene aggiunta o eliminatq nell'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="82164-125">Criticality on a work order is re-calculated each time a work order line is added or deleted on the work order.</span></span>
- <span data-ttu-id="82164-126">Nella visualizzazione dettagli **Tutti gli ordini di lavoro** > visualizzazione **Intestazione** > Scheda dettaglio **Programma**, è possibile selezionare un gruppo di addetti alla manutenzione responsabile o un addetto alla manutenzione responsabile nei campi **Gruppo responsabile** o **Responsabile**.</span><span class="sxs-lookup"><span data-stu-id="82164-126">In **All work orders** Details view > **Header** view > **Schedule** FastTab, you can select a responsible maintenance worker group or a responsible maintenance worker in the **Responsible group** or **Responsible** fields.</span></span> <span data-ttu-id="82164-127">Queste impostazioni possono essere modificate purché l'ordine di lavoro sia attivo, ad esempio, quando lo stato del ciclo di vita di ordine di lavoro cambia.</span><span class="sxs-lookup"><span data-stu-id="82164-127">These settings can be changed as long as the work order is active, for example, when the work order lifecycle state changes.</span></span> <span data-ttu-id="82164-128">La selezione automatica effettuata durante la creazione di ordini di lavoro è basata sull'impostazione in **Addetti alla manutenzione responsabili**.</span><span class="sxs-lookup"><span data-stu-id="82164-128">The automatic selection made during work order creation is based on the setup in **Responsible maintenance workers**.</span></span> <span data-ttu-id="82164-129">Se si aggiungono o rimuovono i processi di ordine di lavoro dopo aver creato un ordine di lavoro e i campi **Gruppo responsabile** e **Responsabile** sono vuoti quando si aggiorna un ordine di lavoro, Gestione cespiti cerca una possibile corrispondenza nel modulo di impostazione per un addetto alla manutenzione o un gruppo di addetti alla manutenzione responsabile.</span><span class="sxs-lookup"><span data-stu-id="82164-129">If you add or remove work order jobs after you have created a work order, and the **Responsible group** field and the **Responsible** field are blank when you update the work order, Asset Management searches for a possible match in the setup form for a responsible maintenance worker group or a responsible maintenance worker.</span></span> <span data-ttu-id="82164-130">Il campo **Gruppo responsabile** o **Responsabile** è già popolato quando si aggiorna l'ordine di lavoro e non viene apportata alcuna modifica.</span><span class="sxs-lookup"><span data-stu-id="82164-130">If the **Responsible group** field or the **Responsible** field is already filled out when you update the work order, no changes are made.</span></span> 

- <span data-ttu-id="82164-131">In **Stato della manutenzione**, è possibile eseguire un calcolo per ottenere una panoramica del carico di lavoro relativo agli ordini di lavoro ricevuti e completati.</span><span class="sxs-lookup"><span data-stu-id="82164-131">In **Maintenance status**, you can make a calculation to get an overview of workload regarding incoming and completed work orders.</span></span>  

- <span data-ttu-id="82164-132">Nella Scheda dettaglio **Dettagli riga**, utilizzare i campi **Longitudine** e **Latitudine** per aggiungere le coordinate geografiche per il cespite nel processo di ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="82164-132">On the **Line details** FastTab, use the **Latitude** and **Longitude** fields to add geographic coordinates for the asset selected on the work order job.</span></span>  

## <a name="create-related-work-order"></a><span data-ttu-id="82164-133">Crea ordine di lavoro correlato</span><span class="sxs-lookup"><span data-stu-id="82164-133">Create related work order</span></span>

<span data-ttu-id="82164-134">È possibile creare un ordine di lavoro associato a un ordine di lavoro esistente se, ad esempio, si intende utilizzare ordini di lavoro principali e secondari.</span><span class="sxs-lookup"><span data-stu-id="82164-134">You can create a related work order to an existing work order if, for example, you want to work with primary and secondary work orders.</span></span> <span data-ttu-id="82164-135">Un nuovo ordine di lavoro è basato su un processo di ordine di lavoro di un ordine di lavoro esistente.</span><span class="sxs-lookup"><span data-stu-id="82164-135">A new work order is based on a work order job from an existing work order.</span></span>

1. <span data-ttu-id="82164-136">Fare clic su **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.</span><span class="sxs-lookup"><span data-stu-id="82164-136">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="82164-137">Selezionare l'ordine di lavoro per il quale si desidera creare un ordine di lavoro correlato.</span><span class="sxs-lookup"><span data-stu-id="82164-137">Select the work order for which you want to make a related work order.</span></span>

3. <span data-ttu-id="82164-138">Fare clic su **Ordine di lavoro correlato**.</span><span class="sxs-lookup"><span data-stu-id="82164-138">Click **Related work order**.</span></span>

4. <span data-ttu-id="82164-139">Nella finestra di dialogo a discesa **Creare ordine di lavoro correlato**, selezionare il processo di ordine di lavoro per il quale si desidera creare un ordine di lavoro correlato nel campo **Processo ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="82164-139">In the **Create related work order** drop-down dialog, select the work order job for which you want to create a related work order in the **Work order job** field.</span></span>

5. <span data-ttu-id="82164-140">Selezionare un tipo di processo di manutenzione nel campo **Tipo di processo di manutenzione** e, se necessario, un settore e una variante di tipi di processo di manutenzione associati nei campi **Settore** e **Variante tipi di processo di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="82164-140">Select a maintenance job type in the **Maintenance job type** field and, if required, a related maintenance job type variant and trade in the **Maintenance job type variant** and **Trade** fields.</span></span>

6. <span data-ttu-id="82164-141">Se si tratta del primo ordine di lavoro correlato creato, fare clic sul pulsante radio **Nuovo ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="82164-141">If this is the first related work order you make, click the **New work order** radio button.</span></span>

7. <span data-ttu-id="82164-142">Selezionare un **Tipo di ordine di lavoro** e una **Descrizione** nei relativi campi.</span><span class="sxs-lookup"><span data-stu-id="82164-142">Select a **Work order type** and a **Description** in the related fields.</span></span>

8. <span data-ttu-id="82164-143">Se necessario, modificare il livello di servizio di ordine di lavoro nel campo **Livello servizio**.</span><span class="sxs-lookup"><span data-stu-id="82164-143">If required, change the work order service level in the **Service level** field.</span></span>

9. <span data-ttu-id="82164-144">Immettere le date di inizio e di fine previste nei campi correlati.</span><span class="sxs-lookup"><span data-stu-id="82164-144">Insert expected start and end dates in the related fields.</span></span>

10. <span data-ttu-id="82164-145">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="82164-145">Click **OK**.</span></span> <span data-ttu-id="82164-146">Il nuovo ordine di lavoro correlato è visualizzato nell'elenco **Tutti gli ordini di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="82164-146">The new related work order is shown in the **All work orders** list.</span></span>

11. <span data-ttu-id="82164-147">Se si crea un ordine di lavoro correlato in un ordine di lavoro che presenta già degli ordini di lavoro correlati, è possibile aggiungere il processo di ordine di lavoro a un ordine di lavoro già correlato.</span><span class="sxs-lookup"><span data-stu-id="82164-147">If you create a related work order on a work order that already has related work orders, you can add the work order job to an already related work order.</span></span> <span data-ttu-id="82164-148">Questa operazione può essere effettuata facendo clic sul pulsante di opzione **Aggiungi a ordine di lavoro correlato** nel passaggio 6.</span><span class="sxs-lookup"><span data-stu-id="82164-148">This is done by clicking the **Add to related work order** radio button in step 6.</span></span> <span data-ttu-id="82164-149">Selezionare quindi l'ordine di lavoro correlato a cui si desidera aggiungere un nuovo processo di ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="82164-149">Then you select the related work order to which you want to add a new work order job.</span></span> <span data-ttu-id="82164-150">Modificare i campi **Livello servizio**, **Data di inizio prevista** e **Data di fine prevista** come necessario e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="82164-150">Edit the **Service level**, **Expected start**, and **Expected end** fields, as required, and click **OK**.</span></span> <span data-ttu-id="82164-151">Il processo di ordine di lavoro viene aggiunto all'ordine di lavoro correlato esistente.</span><span class="sxs-lookup"><span data-stu-id="82164-151">The work order job is added to the existing related work order.</span></span>


![Figura 1](media/03-work-orders.png)

<span data-ttu-id="82164-153">**Nota:** se è stata impostata una maschera di ordine di lavoro correlato in **Parametri di gestione cespiti** >  collegamento **Ordini di lavoro** > campo **Maschera ordini di lavoro correlati**, gli ID di ordine di lavoro saranno creati in conformità con l'impostazione della maschera.</span><span class="sxs-lookup"><span data-stu-id="82164-153">**Note:** If you have set up a related work order mask in **Asset management parameters** > **Work orders** link > **Related work order mask** field, work order IDs will be created in accordance with the mask setup.</span></span> <span data-ttu-id="82164-154">Se non è stata impostata una maschera di ordine di lavoro correlato, per gli ordini di lavoro correlati verrà utilizzato l'ID di ordine di lavoro disponibile successivo.</span><span class="sxs-lookup"><span data-stu-id="82164-154">If no related work order mask is set up, the next available work order ID will be used for related work orders.</span></span>

## <a name="copy-work-order"></a><span data-ttu-id="82164-155">Copia ordine di lavoro</span><span class="sxs-lookup"><span data-stu-id="82164-155">Copy work order</span></span>

<span data-ttu-id="82164-156">È possibile creare rapidamente un nuovo ordine di lavoro da un ordine di lavoro esistente.</span><span class="sxs-lookup"><span data-stu-id="82164-156">It is possible to quickly create a new work order from an existing work order.</span></span> <span data-ttu-id="82164-157">Questo metodo è differente dalla creazione di ordini di lavoro in base a piani di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="82164-157">This way of working with work orders is different from creating work orders based on maintenance plans.</span></span> <span data-ttu-id="82164-158">È utile se, ad esempio, si ha un ordine di lavoro contenente numerosi processi di ordine di lavoro con vari processi in cespiti differenti che devono essere completati a intervalli regolari.</span><span class="sxs-lookup"><span data-stu-id="82164-158">It is useful if, for example, you have a work order containing many work order jobs with various jobs on different assets that should be completed at regular intervals.</span></span>

1. <span data-ttu-id="82164-159">Fare clic su **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.</span><span class="sxs-lookup"><span data-stu-id="82164-159">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="82164-160">Selezionare l'ordine di lavoro da cui copiare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="82164-160">Select the work order from which you want to copy content.</span></span>

3. <span data-ttu-id="82164-161">Fare clic su **Copia ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="82164-161">Click **Copy work order**.</span></span> <span data-ttu-id="82164-162">Viene visualizzata l'impostazione dell'ordine di lavoro selezionato.</span><span class="sxs-lookup"><span data-stu-id="82164-162">The work order setup from the selected work order is shown.</span></span> <span data-ttu-id="82164-163">Se necessario, è possibile modificare alcuni campi.</span><span class="sxs-lookup"><span data-stu-id="82164-163">If required, you can edit some of the fields.</span></span>

4. <span data-ttu-id="82164-164">Fare clic su **OK** per creare il nuovo ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="82164-164">Click **OK** to create the new work order.</span></span>

5. <span data-ttu-id="82164-165">Modificare l'ordine di lavoro in **Tutti gli ordini di lavoro**, se necessario.</span><span class="sxs-lookup"><span data-stu-id="82164-165">Edit the work order in **All work orders**, if required.</span></span>

>[!NOTE]
><span data-ttu-id="82164-166">Quando si crea il nuovo ordine di lavoro, alcune informazioni vengono copiate direttamente dall'ordine di lavoro esistente.</span><span class="sxs-lookup"><span data-stu-id="82164-166">When the new work order is created, some information is copied directly from the existing work order.</span></span> <span data-ttu-id="82164-167">Le informazioni relative a previsioni, strumenti, elenchi di controllo di manutenzione, unità funzionale, indirizzi e programmazione non vengono copiate, ma inizializzate dall'impostazione corrente in Gestione cespiti.</span><span class="sxs-lookup"><span data-stu-id="82164-167">Information regarding forecasts, tools, maintenance checklists, functional location, addresses, and scheduling is not copied, but initialized from the current setup in Asset Management.</span></span> <span data-ttu-id="82164-168">Ciò significa che se le modifiche sono state eseguite in quei dati dalla creazione del primo ordine di lavoro fino alla creazione di una copia dell'ordine di lavoro, sono incluse nel nuovo ordine di lavoro creato.</span><span class="sxs-lookup"><span data-stu-id="82164-168">This means that if changes were made in those data from the time of creation of the first work order until the time you made a copy of the work order, those changes are included in the new work order you have created.</span></span> <span data-ttu-id="82164-169">Esempi di questa operazione sono le modifiche nelle previsioni o negli elenchi di controllo di manutenzione aggiornati.</span><span class="sxs-lookup"><span data-stu-id="82164-169">Examples are changes in forecasts or updated maintenance checklists.</span></span>


![Figura 2](media/04-work-orders.png)


## <a name="create-work-order-based-on-a-maintenance-request"></a><span data-ttu-id="82164-171">Creare un ordine di lavoro basato su una richiesta di intervento di manutenzione</span><span class="sxs-lookup"><span data-stu-id="82164-171">Create work order based on a maintenance request</span></span>

1. <span data-ttu-id="82164-172">Fare clic su **Gestione cespiti** > **Comune** > **Richieste di intervento di manutenzione** > **Tutte le richieste di intervento di manutenzione** o **Richieste di intervento di manutenzione attive**.</span><span class="sxs-lookup"><span data-stu-id="82164-172">Click **Asset management** > **Common** > **Maintenance requests** > **All maintenance requests** or **Active maintenance requests**.</span></span>

2. <span data-ttu-id="82164-173">Selezionare la richiesta di intervento di manutenzione per la quale si desidera creare un ordine di lavoro e fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="82164-173">Select the maintenance request for which you want to create a work order, and click **Edit**.</span></span>

3. <span data-ttu-id="82164-174">In **Tutte le richieste**, fare clic su **Ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="82164-174">In **All requests**, click **Work order**.</span></span>

4. <span data-ttu-id="82164-175">Popolare i campi in **Ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="82164-175">Fill out the **Work order** drop-down.</span></span> <span data-ttu-id="82164-176">Se un tipo di processo di manutenzione è stato selezionato nella richiesta di intervento di manutenzione, è possibile selezionare un altro tipo di processo di manutenzione, se necessario, quando si crea l'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="82164-176">If a maintenance job type has been selected in the maintenance request, you are able to select another maintenance job type, if required, when you create the work order.</span></span>

5. <span data-ttu-id="82164-177">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="82164-177">Click **OK**.</span></span> <span data-ttu-id="82164-178">Viene visualizzato un messaggio che informa della creazione dell'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="82164-178">You will see a message informing you that the work order has been created.</span></span>

6. <span data-ttu-id="82164-179">Se si desidera visualizzare gli ordini di lavoro collegati a una richiesta di intervento di manutenzione, selezionare la richiesta di intervento di manutenzione negli elenchi **Tutte le richiesta di intervento di manutenzione** o **Richieste di intervento di manutenzione attive** e fare clic sui pulsanti **Ordini di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="82164-179">If you want to see which work orders are connected to a maintenance request, select the maintenance request in the **All maintenance requests** or **Active maintenance requests** lists, and click the **Work orders** button.</span></span>


![Figura 3](media/05-work-orders.png)


>[!NOTE]
><span data-ttu-id="82164-181">Gli ordini di lavoro possono anche essere generati automaticamente programmando processi di piano di manutenzione o impostando "Crea automaticamente" per i piani di manutenzione o i cicli di manutenzione di un cespite.</span><span class="sxs-lookup"><span data-stu-id="82164-181">Work orders can also be created automatically by scheduling maintenance plan jobs, or by setting up "Auto create" maintenance plans or maintenance rounds on an asset.</span></span> <span data-ttu-id="82164-182">Gli ordini di lavoro creati dalle richieste di intervento di manutenzione in **Programma di manutenzione** vengono creati con i tipi di processo di manutenzione selezionati nelle richieste di intervento di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="82164-182">Work orders created from maintenance requests in **Maintenance schedule** are created with the maintenance job types selected in the maintenance requests.</span></span>

