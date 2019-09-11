---
title: Pool di ordini di lavoro
description: In questo argomento viene descritto come utilizzare pool di ordini di lavoro in Gestione cespiti.
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
ms.openlocfilehash: 069fa02073808fd7bbaac9bc1603e49ce4d450eb
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875736"
---
# <a name="work-order-pools"></a><span data-ttu-id="e85f4-103">Pool di ordini di lavoro</span><span class="sxs-lookup"><span data-stu-id="e85f4-103">Work order pools</span></span>


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="e85f4-104">È possibile utilizzare pool di ordini di lavoro per raggruppare ordini di lavoro che hanno qualcosa in comune.</span><span class="sxs-lookup"><span data-stu-id="e85f4-104">You can use work order pools to group work orders that have something in common.</span></span> <span data-ttu-id="e85f4-105">Ad esempio, è possibile creare pool di ordini di lavoro per</span><span class="sxs-lookup"><span data-stu-id="e85f4-105">For example, you can create work order pools for</span></span>

- <span data-ttu-id="e85f4-106">squadra di lavoro, ad esempio, Squadra di manutenzione A, Squadra di manutenzione B</span><span class="sxs-lookup"><span data-stu-id="e85f4-106">work crews, for example, Maintenance Crew A, Maintenance Crew B</span></span>  

- <span data-ttu-id="e85f4-107">competenze professionali, ad esempio, elettricisti o idraulici</span><span class="sxs-lookup"><span data-stu-id="e85f4-107">professional skills, for example, electricians or plumbers</span></span>  

- <span data-ttu-id="e85f4-108">ubicazioni fisiche</span><span class="sxs-lookup"><span data-stu-id="e85f4-108">physical locations</span></span>  

- <span data-ttu-id="e85f4-109">pianificazioni temporali ad esempio, settimane o altri periodi</span><span class="sxs-lookup"><span data-stu-id="e85f4-109">time schedules, for example, weeks or other periods</span></span>  


<span data-ttu-id="e85f4-110">Se necessario, un ordine di lavoro può essere inserito in molti pool di ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e85f4-110">If required, one work order can be placed in many work order pools.</span></span>


## <a name="create-work-order-pool"></a><span data-ttu-id="e85f4-111">Creare pool di ordini di lavoro</span><span class="sxs-lookup"><span data-stu-id="e85f4-111">Create work order pool</span></span>

<span data-ttu-id="e85f4-112">In **Tutti i pool di ordini di lavoro** o **Pool di ordini di lavoro attivi**, è possibile ottenere una panoramica dei pool di ordini di lavoro e creare nuovi pool.</span><span class="sxs-lookup"><span data-stu-id="e85f4-112">In **All work order pools** or **Active work order pools**, you can get an overview of your work order pools and create new pools.</span></span>

1. <span data-ttu-id="e85f4-113">Fare clic su **Gestione cespiti** > **Comune** > **Pool di ordini di lavoro** > **Tutti i pool di ordini di lavoro** o **Pool di ordini di lavoro attivi**.</span><span class="sxs-lookup"><span data-stu-id="e85f4-113">Click **Asset management** > **Common** > **Work order pools** > **All work order pools** or **Active work order pools**.</span></span>

2. <span data-ttu-id="e85f4-114">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e85f4-114">Click **New**.</span></span>

3. <span data-ttu-id="e85f4-115">Immettere un ID di pool di ordine di lavoro nel campo **Pool** e un nome nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="e85f4-115">Insert a work order pool ID in the **Pool** field and a name in the **Name** field.</span></span>

4. <span data-ttu-id="e85f4-116">Impostare l'interruttore **Attivo** su "Sì" per indicare che il pool di ordini di lavoro è attivo.</span><span class="sxs-lookup"><span data-stu-id="e85f4-116">Select "Yes" on the **Active** toggle button to indicate that the work order pool is active.</span></span>

5. <span data-ttu-id="e85f4-117">Impostare l'interruttore **Elimina relazioni di ordini di lavoro** su "Sì" se gli ordini di lavoro devono essere rimossi automaticamente dal pool di ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e85f4-117">Select "Yes" on the **Delete work order relations** toggle button if you want work orders to be automatically removed from the work order pool.</span></span>

6. <span data-ttu-id="e85f4-118">Nel campo **Elimina stato del ciclo di vita**, selezionare lo stato del ciclo di vita di ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e85f4-118">In the **Delete lifecycle state** field, select the work order lifecycle state.</span></span> <span data-ttu-id="e85f4-119">Ad esempio, lo stato del ciclo di vita di ordine di lavoro per il completamento di un ordine di lavoro può essere impostato per eliminare automaticamente le relazioni con pool di ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e85f4-119">For example, the work order lifecycle state for completing a work order could be set to automatically delete relations to work order pools.</span></span>

7. <span data-ttu-id="e85f4-120">È possibile iniziare a aggiungere ordini di lavoro al pool di ordini di lavoro utilizzato immediatamente.</span><span class="sxs-lookup"><span data-stu-id="e85f4-120">You can start adding work orders to your work order pool right away.</span></span> <span data-ttu-id="e85f4-121">Nella Scheda dettaglio **Ordini di lavoro** fare clic su **Aggiungi riga**.</span><span class="sxs-lookup"><span data-stu-id="e85f4-121">On the **Work orders** FastTab, click **Add line**.</span></span>

8. <span data-ttu-id="e85f4-122">Selezionare un ordine di lavoro nel campo **Ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="e85f4-122">Select a work order in the **Work order** field.</span></span> <span data-ttu-id="e85f4-123">I campi correlati vengono aggiornati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e85f4-123">The related fields are automatically updated.</span></span>

9. <span data-ttu-id="e85f4-124">Ripetere i passaggi da 7 a 8 per aggiungere più ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e85f4-124">Repeat steps 7-8 if you want to add more work orders.</span></span>

10. <span data-ttu-id="e85f4-125">Nel campo **Ordinamento**, è possibile indicare se gli ordini di lavoro devono essere eseguiti in un determinato ordine.</span><span class="sxs-lookup"><span data-stu-id="e85f4-125">In the **Sort order** field, you can indicate if the work orders should be carried out in a certain order.</span></span> <span data-ttu-id="e85f4-126">Inserire i numeri 1, 2, 3 e così via per indicare una sequenza specifica per gli ordini di lavoro selezionati.</span><span class="sxs-lookup"><span data-stu-id="e85f4-126">Insert numbers 1, 2, 3, and so on to indicate a specific sequence for the selected work orders.</span></span>

11. <span data-ttu-id="e85f4-127">Fare clic sul pulsante **Ordini di lavoro** per visualizzare un elenco di tutti gli ordini di lavoro inclusi nel pool di ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e85f4-127">Click the **Work orders** button to see a list of all the work orders included in the work order pool.</span></span>

12. <span data-ttu-id="e85f4-128">Fare clic sul pulsante **Carico di capacità** per aprire **Carico di capacità** in modo da calcolare e visualizzare il carico di capacità per il programma di manutenzione, gli ordini di lavoro non programmati e gli ordini di lavoro programmati.</span><span class="sxs-lookup"><span data-stu-id="e85f4-128">Click the **Capacity load** button to open **Capacity load** to calculate and view capacity load for maintenance schedule, not-scheduled work orders, and scheduled work orders.</span></span>

13. <span data-ttu-id="e85f4-129">Fare clic sul pulsante **Previsione articolo** per aprire **Previsione articolo** in modo da calcolare e visualizzare le previsioni per articoli (pezzi di ricambio e altri articoli necessari) correlate al programma di manutenzione, agli ordini di lavoro non programmati e agli ordini di lavoro programmati.</span><span class="sxs-lookup"><span data-stu-id="e85f4-129">Click the **Item forecast** button to open **Item forecast** to calculate and view forecasts for items (spare parts and other required items) related to maintenance schedule, not-scheduled work orders, and scheduled work orders.</span></span>

14. <span data-ttu-id="e85f4-130">Fare clic sul pulsante **Richiesta di acquisto ordine di lavoro** per aprire l'elenco **Richiesta di acquisto ordine di lavoro** allo scopo di visualizzare un elenco delle richieste di acquisto correlate agli ordini di lavoro nel pool di ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e85f4-130">Click the **Work order purchase requisition** button to open the **Work order purchase requisition** list to see a list of purchase requisitions related to the work orders in the work order pool.</span></span>

15. <span data-ttu-id="e85f4-131">Fare clic sul pulsante **Acquisto ordine di lavoro** per aprire l'elenco **Acquisto ordine di lavoro** per visualizzare un elenco di ordini di lavoro correlati agli ordini di lavoro nel pool di ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e85f4-131">Click the **Work order purchase** button to open the **Work order purchase** list to see a list of purchase orders related to the work orders in the work order pool.</span></span>

>[!NOTE]
><span data-ttu-id="e85f4-132">Quando un pool di ordini di lavoro non è più appropriato per la pianificazione del lavoro, impostare la casella di controllo **Attivo** di quel pool su "No" nella visualizzazione elenco **Pool di ordini di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="e85f4-132">When a work order pool is no longer relevant for your work planning, set the **Active** check box for that pool to "No" in the **Work order pool** list view.</span></span>

<span data-ttu-id="e85f4-133">Selezionare la casella di controllo **Elimina relazioni di ordini di lavoro** se si desidera eliminare tutte le righe di ordine di lavoro, ad esempio per creare un pool vuoto utilizzabile successivamente per altri ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e85f4-133">Select the **Delete work order relations** check box if you want to delete all work order lines, for example to create an empty pool that you can later use for other work orders.</span></span> <span data-ttu-id="e85f4-134">Deselezionare la casella di controllo **Elimina relazioni di ordini di lavoro** se si desidera utilizzare il pool di ordini di lavoro per creare nuove relazioni di ordine di lavoro in seguito.</span><span class="sxs-lookup"><span data-stu-id="e85f4-134">Remember to clear the **Delete work order relations** check box if you want to use the work order pool to create new work order relations later.</span></span>


![Figura 1](media/22-work-orders.png)


## <a name="add-work-order-to-a-work-order-pool"></a><span data-ttu-id="e85f4-136">Aggiungere un ordine di lavoro a un pool di ordini di lavoro</span><span class="sxs-lookup"><span data-stu-id="e85f4-136">Add work order to a work order pool</span></span>

<span data-ttu-id="e85f4-137">Come descritto nella sezione precedente, è possibile aggiungere ordini di lavoro a un pool di ordini di lavoro quando si crea il pool.</span><span class="sxs-lookup"><span data-stu-id="e85f4-137">As described in the section above, you can add work orders to a work order pool when you create the pool.</span></span> <span data-ttu-id="e85f4-138">È inoltre possibile aggiungere un ordine di lavoro a un pool di ordini di lavoro dall'elenco **Tutti gli ordini di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="e85f4-138">You can also add a work order to a work order pool from one of the **All work orders** list.</span></span>

1. <span data-ttu-id="e85f4-139">Fare clic su **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.</span><span class="sxs-lookup"><span data-stu-id="e85f4-139">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="e85f4-140">Selezionare l'ordine di lavoro nell'elenco e fare clic su **Pool di ordini di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="e85f4-140">Select the work order in the list, and click **Work order pool**.</span></span>

3. <span data-ttu-id="e85f4-141">Selezionare "Aggiungi" nel campo **Aggiungi/rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="e85f4-141">Select "Add" in the **Add/remove** field.</span></span>

4. <span data-ttu-id="e85f4-142">Selezionare il pool di ordini di lavoro nel campo **Pool**.</span><span class="sxs-lookup"><span data-stu-id="e85f4-142">Select the work order pool in the **Pool** field.</span></span>

5. <span data-ttu-id="e85f4-143">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e85f4-143">Click **OK**.</span></span>

6. <span data-ttu-id="e85f4-144">Dopo aver aggiunto un ordine di lavoro a un pool di ordini di lavoro, se si desidera inserire un ordine di lavoro in una sequenza specifica nel pool: aprire una delle pagine elenco dei pool di ordini di lavoro, selezionare il pool e fare clic su **Modifica** e modificare l'ordinamento degli ordini di lavoro inclusi nel pool nel modulo **Pool di ordini di lavoro** > Scheda dettaglio **Ordini di lavoro** > campo **Ordinamento**.</span><span class="sxs-lookup"><span data-stu-id="e85f4-144">After you have added a work order to a work order pool, if you want to place the work order in a specific sequence in the pool: Open one of the work order pools list pages, select the pool and click **Edit**, and adjust the sort order of the work orders included in pool in the **Work order pool** form > **Work orders** FastTab > **Sort order** field.</span></span>

<span data-ttu-id="e85f4-145">Se si intende rimuovere l'ordine di lavoro selezionato da un pool di ordini di lavoro, selezionare "Rimuovi" nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="e85f4-145">If you want to remove the selected work order from a work order pool, select "Remove" in step 3.</span></span>

