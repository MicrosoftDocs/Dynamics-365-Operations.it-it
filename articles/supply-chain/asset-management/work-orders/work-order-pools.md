---
title: Pool di ordini di lavoro
description: In questo argomento viene descritto come utilizzare pool di ordini di lavoro in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderTablePoolPart, EntAssetWorkOrderPoolReferenceInfoPart, EntAssetWorkOrderPool, EntAssetWorkOrderPoolPreviewPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: afea5b8d0f958c3ab53d6cef8c9a0e9030d7c67b
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2021
ms.locfileid: "5017519"
---
# <a name="work-order-pools"></a><span data-ttu-id="3a14b-103">Pool di ordini di lavoro</span><span class="sxs-lookup"><span data-stu-id="3a14b-103">Work order pools</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="3a14b-104">È possibile utilizzare pool di ordini di lavoro per raggruppare ordini di lavoro che hanno qualcosa in comune.</span><span class="sxs-lookup"><span data-stu-id="3a14b-104">You can use work order pools to group work orders that have something in common.</span></span> <span data-ttu-id="3a14b-105">Di seguito sono riportati alcuni esempi di elementi per i quali è possibile creare i pool di ordini di lavoro:</span><span class="sxs-lookup"><span data-stu-id="3a14b-105">Here are some examples of things that you can create  work order pools for:</span></span>

- <span data-ttu-id="3a14b-106">Squadra di lavoro, ad esempio, Squadra di manutenzione A o Squadra di manutenzione B</span><span class="sxs-lookup"><span data-stu-id="3a14b-106">Work crews, for example, Maintenance Crew A or Maintenance Crew B</span></span>  

- <span data-ttu-id="3a14b-107">Competenze professionali, ad esempio, elettricisti o idraulici</span><span class="sxs-lookup"><span data-stu-id="3a14b-107">Professional skills, such as electricians or plumbers</span></span>  

- <span data-ttu-id="3a14b-108">Ubicazioni fisiche</span><span class="sxs-lookup"><span data-stu-id="3a14b-108">Physical locations</span></span>  

- <span data-ttu-id="3a14b-109">Pianificazioni temporali ad esempio, settimane o altri periodi</span><span class="sxs-lookup"><span data-stu-id="3a14b-109">Time schedules, such as weeks or other periods</span></span>  

<span data-ttu-id="3a14b-110">Se necessario, è possibile inserire un ordine di lavoro in più pool di ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3a14b-110">As you require, you can put one work order in multiple work order pools.</span></span>


## <a name="create-a-work-order-pool"></a><span data-ttu-id="3a14b-111">Creare un pool di ordini di lavoro</span><span class="sxs-lookup"><span data-stu-id="3a14b-111">Create a work order pool</span></span>

<span data-ttu-id="3a14b-112">Nella pagina elenco **Tutti i pool di ordini di lavoro** o **Pool di ordini di lavoro attivi**, è possibile ottenere una panoramica dei pool di ordini di lavoro e creare nuovi pool.</span><span class="sxs-lookup"><span data-stu-id="3a14b-112">On the **All work order pools** or **Active work order pools** list page, you can get an overview of your work order pools and create new pools.</span></span>

1. <span data-ttu-id="3a14b-113">Selezionare **Gestione cespiti** > **Comune** > **Pool di ordini di lavoro** > **Tutti i pool di ordini di lavoro** o **Pool di ordini di lavoro attivi**.</span><span class="sxs-lookup"><span data-stu-id="3a14b-113">Select **Asset management** > **Common** > **Work order pools** > **All work order pools** or **Active work order pools**.</span></span>

2. <span data-ttu-id="3a14b-114">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="3a14b-114">Select **New**.</span></span>

3. <span data-ttu-id="3a14b-115">Nel campo **Pool** immettere un ID per il pool di ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3a14b-115">In the **Pool** field, enter an ID for the work order pool.</span></span>

4. <span data-ttu-id="3a14b-116">Nel campo **Nome** immettere un nome.</span><span class="sxs-lookup"><span data-stu-id="3a14b-116">the **Name** field, enter a name.</span></span>

5. <span data-ttu-id="3a14b-117">Impostare l'opzione **Attivo** su **Sì** per indicare che il pool di ordini di lavoro è attivo.</span><span class="sxs-lookup"><span data-stu-id="3a14b-117">Set the **Active** option to **Yes** to indicate that the work order pool is active.</span></span>

6. <span data-ttu-id="3a14b-118">Impostare l'opzione **Elimina relazioni di ordini di lavoro** su **Sì** se gli ordini di lavoro devono essere rimossi automaticamente dal pool di ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3a14b-118">Set the **Delete work order relations** option to **Yes** if work orders should automatically be removed from the work order pool.</span></span>

7. <span data-ttu-id="3a14b-119">Nel campo **Elimina stato del ciclo di vita**, selezionare lo stato del ciclo di vita di ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3a14b-119">In the **Delete lifecycle state** field, select the work order lifecycle state.</span></span> <span data-ttu-id="3a14b-120">Ad esempio, lo stato del ciclo di vita di ordine di lavoro per il completamento di un ordine di lavoro può essere impostato per eliminare automaticamente le relazioni con pool di ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3a14b-120">For example, the work order lifecycle state for completing a work order could be set to automatically delete relations to work order pools.</span></span>

    <span data-ttu-id="3a14b-121">È possibile iniziare a aggiungere ordini di lavoro al pool di ordini di lavoro utilizzato immediatamente.</span><span class="sxs-lookup"><span data-stu-id="3a14b-121">You can start adding work orders to your work order pool right away.</span></span>

8. <span data-ttu-id="3a14b-122">Nella Scheda dettaglio **Ordini di lavoro** selezionare **Aggiungi riga**.</span><span class="sxs-lookup"><span data-stu-id="3a14b-122">On the **Work orders** FastTab, select **Add line**.</span></span>

9. <span data-ttu-id="3a14b-123">Selezionare un ordine di lavoro nel campo **Ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="3a14b-123">In the **Work order** field, select a work order.</span></span> <span data-ttu-id="3a14b-124">I campi correlati vengono aggiornati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3a14b-124">The related fields are automatically updated.</span></span>

10. <span data-ttu-id="3a14b-125">Ripetere i passaggi da 8 a 9 per aggiungere ulteriori ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3a14b-125">Repeat steps 8 through 9 to add more work orders.</span></span>

11. <span data-ttu-id="3a14b-126">Se gli ordini di lavoro aggiunti devono essere eseguiti in un ordine specifico, nel campo **Ordinamento** immettere i numeri **1**, **2**, **3** e così via per specificare l'ordine.</span><span class="sxs-lookup"><span data-stu-id="3a14b-126">If the work orders that you added should be done in a specific order, in the **Sort order** field, you can enter the numbers **1**, **2**, **3**, and so on, to specify that order.</span></span>

12. <span data-ttu-id="3a14b-127">Per visualizzare un elenco di tutti gli ordini di lavoro inclusi nel pool di ordini di lavoro, nel riquadro azioni, nella scheda **Pool di ordini di lavoro**, nel gruppo **Visualizza pool di ordini di lavoro correlato**, selezionare **Ordini di lavoro** per aprire la pagina elenco **Tutti gli ordini di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="3a14b-127">To view a list of all the work orders that are included in the work order pool, on the Action Pane, on the **Work order pool** tab, in the **View work order pool related** group, select **Work orders** to open the **All work orders** list page.</span></span>

13. <span data-ttu-id="3a14b-128">Per calcolare e visualizzare il carico di capacità per la programmazione della manutenzione, gli ordini di lavoro non programmati e gli ordini di lavoro programmati, nel riquadro azioni, nella scheda **Pool di ordini di lavoro**, nel gruppo **Visualizza pool di ordini di lavoro correlato**, scegliere **Carico capacità** per aprire la finestra di dialogo **Calcola carico di capacità**.</span><span class="sxs-lookup"><span data-stu-id="3a14b-128">To calculate and view capacity load for the maintenance schedule, unscheduled work orders, and scheduled work orders, on the Action Pane, on the **Work order pool** tab, in the **View work order pool related** group, select **Capacity load** to open the **Calculate capacity load** dialog.</span></span>

14. <span data-ttu-id="3a14b-129">Per calcolare e visualizzare le previsioni per gli articoli (parti di ricambio e altri articoli richiesti) correlati alla programmazione della manutenzione, agli ordini di lavoro non programmati e agli ordini di lavoro programmati, nel riquadro azioni, nella scheda **Pool di ordini di lavoro**, nel gruppo **Visualizza pool di ordini di lavoro correlato**, scegliere **Previsione articolo** per aprire la finestra di dialogo **Calcolare previsioni articolo**.</span><span class="sxs-lookup"><span data-stu-id="3a14b-129">To calculate and view forecasts for items (spare parts and other required items) that are related to maintenance schedule, unscheduled work orders, and scheduled work orders, on the Action Pane, on the **Work order pool** tab, in the **View work order pool related** group, select **Item forecast** to open the **Calculate item forecast** dialog.</span></span>

15. <span data-ttu-id="3a14b-130">Per visualizzare un elenco di richieste di acquisto correlate agli ordini di lavoro nel pool di ordini di lavoro, nel riquadro azioni, nella scheda **Pool di ordini di lavoro**, nel gruppo **Approvvigionamento**, selezionare **Richiesta di acquisto ordine di lavoro** per aprire la pagina elenco **Richiesta di acquisto ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="3a14b-130">To view a list of purchase requisitions that are related to the work orders in the work order pool, on the Action Pane, on the **Work order pool** tab, in the **Procurement** group, select **Work order purchase requisition** to open the **Work order purchase requisition** list page.</span></span>

16. <span data-ttu-id="3a14b-131">Per visualizzare un elenco di ordini fornitore correlati agli ordini di lavoro nel pool di ordini di lavoro, nel riquadro azioni, nella scheda **Pool di ordini di lavoro**, nel gruppo **Approvvigionamento**, selezionare **Acquisto ordine di lavoro** per aprire la pagina elenco **Acquisto ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="3a14b-131">To view a list of purchase orders that are related to the work orders in the work order pool, on the Action Pane, on the **Work order pool** tab, in the **Procurement** group, select **Work order purchase** to open the **Work order purchase** list page.</span></span>

>[!NOTE]
><span data-ttu-id="3a14b-132">Quando un pool di ordini di lavoro non è più appropriato per la pianificazione del lavoro, impostare l'opzione **Attivo** di quel pool su **No** nella pagina **Pool di ordini di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="3a14b-132">When a work order pool is no longer relevant to your work planning, set the **Active** option for that pool to **No** in the list view of the **Work order pool** page.</span></span>

<span data-ttu-id="3a14b-133">Per eliminare tutte le righe degli ordini di lavoro, impostare l'opzione **Elimina relazioni di ordini di lavoro** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="3a14b-133">To delete all worker order lines, set the **Delete work order relations** option to **Yes**.</span></span> <span data-ttu-id="3a14b-134">Questa opzione è utile se, ad esempio, si desidera creare un pool vuoto da utilizzare in seguito per altri ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3a14b-134">This option is useful if, for example, you want to create an empty pool that you can use later for other work orders.</span></span> <span data-ttu-id="3a14b-135">Quando si è pronti per utilizzare il pool di ordini di lavoro per creare nuove relazioni di ordini di lavoro in un secondo momento, ricordare di impostare l'opzione **Elimina relazioni di ordini di lavoro** su **No**.</span><span class="sxs-lookup"><span data-stu-id="3a14b-135">When you're ready to use the work order pool to create new work order relations later, remember to set the **Delete work order relations** option to **No**.</span></span>

<span data-ttu-id="3a14b-136">Nell'illustrazione seguente è illustrato un esempio della pagina elenco **Pool di ordini di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="3a14b-136">The illustration below shows an example of the **Work order pool** list page.</span></span>

![Figura 1](media/22-work-orders.png)


## <a name="add-a-work-order-to-a-work-order-pool"></a><span data-ttu-id="3a14b-138">Aggiungere un ordine di lavoro a un pool di ordini di lavoro</span><span class="sxs-lookup"><span data-stu-id="3a14b-138">Add a work order to a work order pool</span></span>

<span data-ttu-id="3a14b-139">Come descritto nella sezione precedente, è possibile aggiungere ordini di lavoro a un pool di ordini di lavoro quando si crea il pool.</span><span class="sxs-lookup"><span data-stu-id="3a14b-139">As described in the previous section, you can add work orders to a work order pool when you create that pool.</span></span> <span data-ttu-id="3a14b-140">È inoltre possibile aggiungere ordini di lavoro a un pool di ordini di lavoro nella pagina elenco **Ordini di lavoro attivi** o **Tutti gli ordini di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="3a14b-140">You can also add work orders to a work order pool on the **All work orders** or **Active work orders** list page.</span></span>

1. <span data-ttu-id="3a14b-141">Selezionare l'ordine di lavoro, quindi nel riquadro azioni, nella scheda **Ordine di lavoro**, nel gruppo **Gestisci**, selezionare **Pool di ordini di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="3a14b-141">Select the work order, and then, on the Action Pane, on the **Work order** tab, in the **Maintain** group, select **Work order pool**.</span></span>

2. <span data-ttu-id="3a14b-142">Selezionare l'ordine di lavoro nell'elenco e fare clic su **Pool di ordini di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="3a14b-142">Select the work order in the list, and click **Work order pool**.</span></span>

3. <span data-ttu-id="3a14b-143">Nella finestra di dialogo **Gestisci pool di ordini di lavoro**, nel campo **Aggiungi/Rimuovi**, selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="3a14b-143">In the **Maintain work order pool** dialog, in the **Add/remove** field, select **Add**.</span></span>

4. <span data-ttu-id="3a14b-144">Selezionare il pool di ordini di lavoro nel campo **Pool**.</span><span class="sxs-lookup"><span data-stu-id="3a14b-144">In the **Pool** field, select the work order pool.</span></span>

5. <span data-ttu-id="3a14b-145">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="3a14b-145">Select **OK**.</span></span>

6. <span data-ttu-id="3a14b-146">Per inserire l'ordine di lavoro aggiunto in un ordine specifico del pool di ordini di lavoro, nella pagina elenco **Pool di ordini di lavoro attivi** o **Tutti i pool di ordini di lavoro**, selezionare il pool e **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="3a14b-146">To put the work order that you added in a specific order in the work order pool, on the **All work order pools** or **Active work order pools** list page, select the pool, and then select **Edit**.</span></span> <span data-ttu-id="3a14b-147">Quindi, nella pagina **Pool di ordini di lavoro**, nella Scheda dettaglio **Ordini di lavoro**, utilizzare il campo **Ordinamento** per modificare l'ordinamento degli ordini di lavoro inclusi nel pool.</span><span class="sxs-lookup"><span data-stu-id="3a14b-147">Then, on the **Work order pool** page, on the **Work orders** FastTab, use the **Sort order** field to adjust the sort order of the work orders that are included in pool.</span></span>

<span data-ttu-id="3a14b-148">Per rimuovere un ordine di lavoro da un pool di ordini di lavoro, ripetere questi passaggi, ma selezionare **Rimuovi** nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="3a14b-148">To remove a work order from a work order pool, repeat these steps, but select **Remove** in step 3.</span></span>

