---
title: Programmare capacità carico di lavoro
description: In questo argomento viene descritto come impostare e programmare la capacità di carico di lavoro per i lavoratori di un magazzino o per un intero magazzino.
author: MarkusFogelberg
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSWorkloadCapacity
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4eac4838a4df8f1f5863f1ce1895e7aded5fb08b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5239280"
---
# <a name="schedule-workload-capacity"></a><span data-ttu-id="f1d19-103">Programmare capacità carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="f1d19-103">Schedule workload capacity</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="f1d19-104">È possibile pianificare la capacità del carico di lavoro per i magazzini nonché proiettare i carichi di lavoro correnti e futuri per i lavoratori nei singoli magazzini.</span><span class="sxs-lookup"><span data-stu-id="f1d19-104">You can schedule workload capacity for warehouses, and you can also project the current and future workloads for the workers in individual warehouses.</span></span> <span data-ttu-id="f1d19-105">È possibile proiettare il carico di lavoro per l'intero magazzino, oppure proiettare separatamente il carico di lavoro per i carichi di lavoro in ingresso e in uscita.</span><span class="sxs-lookup"><span data-stu-id="f1d19-105">You can project the workload for the whole warehouse, or you can project the workload separately for incoming and outgoing workloads.</span></span>

<span data-ttu-id="f1d19-106">Per proiettare il carico di lavoro in uscita per i magazzini selezionati, devono essere disponibili i dati della programmazione generale per tali magazzini.</span><span class="sxs-lookup"><span data-stu-id="f1d19-106">To project workload output for selected warehouses, master scheduling data must be available for those warehouses.</span></span> <span data-ttu-id="f1d19-107">Per ulteriori informazioni, vedere [Panoramica dei piani generali](../master-planning/master-plans.md).</span><span class="sxs-lookup"><span data-stu-id="f1d19-107">For more information, see [Master plans overview](../master-planning/master-plans.md).</span></span>

## <a name="schedule-and-view-workloads-for-a-warehouse"></a><span data-ttu-id="f1d19-108">Pianificare e visualizzare i carichi di lavoro per un magazzino</span><span class="sxs-lookup"><span data-stu-id="f1d19-108">Schedule and view workloads for a warehouse</span></span>

<span data-ttu-id="f1d19-109">Per pianificare la capacità del carico di lavoro per un magazzino, creare un'impostazione del carico di lavoro per uno o più magazzini, quindi associare l'impostazione del carico di lavoro a un piano generale.</span><span class="sxs-lookup"><span data-stu-id="f1d19-109">To schedule workload capacity for a warehouse, you create a workload setup for one or more warehouses, and then associate the workload setup with a master plan.</span></span> <span data-ttu-id="f1d19-110">Nell'impostazione della capacità del carico di lavoro, è possibile definire i limiti di peso o volume per le transazioni in entrata e in uscita.</span><span class="sxs-lookup"><span data-stu-id="f1d19-110">In the workload capacity setup, you can define limits for the weight or volume for incoming and outgoing transactions.</span></span> <span data-ttu-id="f1d19-111">È inoltre possibile creare più impostazioni per ciascun magazzino e associare l'impostazione ai singoli piani generali.</span><span class="sxs-lookup"><span data-stu-id="f1d19-111">You can also create more than one setup for each warehouse and then associate the setup with individual master plans.</span></span> <span data-ttu-id="f1d19-112">Ad esempio, è possibile utilizzare questo approccio per essere conformi alle modifiche stagionali nella forza lavoro.</span><span class="sxs-lookup"><span data-stu-id="f1d19-112">For example, you might use this approach to accommodate seasonal changes in the workforce.</span></span>

<span data-ttu-id="f1d19-113">Se i lavoratori di un magazzino lavorano con transazioni sia per i carichi di lavoro in ingresso che in uscita, è possibile configurare le impostazioni di capacità del magazzino di modo che il carico di lavoro è proiettato in una visualizzazione combinata.</span><span class="sxs-lookup"><span data-stu-id="f1d19-113">If the workers for a warehouse work with transactions for both incoming and outgoing workloads, you can configure the warehouse capacity setup so that the workload is projected in a combined view.</span></span>

<span data-ttu-id="f1d19-114">Per pianificare e visualizzare i carichi di lavoro per i magazzini, è necessario completare le seguenti attività:</span><span class="sxs-lookup"><span data-stu-id="f1d19-114">To schedule and view workloads for warehouses, you must complete the following tasks:</span></span>

1. <span data-ttu-id="f1d19-115">Creare un'impostazione di capacità del carico di lavoro e definirne i limiti di capacità per uno o più magazzini.</span><span class="sxs-lookup"><span data-stu-id="f1d19-115">Create a workload capacity setup and define workload capacity limits for one or more warehouses.</span></span>
2. <span data-ttu-id="f1d19-116">Associare le impostazioni di capacità del carico di lavoro con un piano generale per creare le proiezioni del carico di lavoro e specificare il tempo durante il quale verranno applicate queste proiezioni.</span><span class="sxs-lookup"><span data-stu-id="f1d19-116">Associate the workload capacity setup with a master plan to create workload projections and specify how long those projections will apply.</span></span>

### <a name="create-a-workload-capacity-setup-for-a-warehouse"></a><span data-ttu-id="f1d19-117">Creare un'impostazione di capacità del carico di lavoro per un magazzino</span><span class="sxs-lookup"><span data-stu-id="f1d19-117">Create a workload capacity setup for a warehouse</span></span>

1. <span data-ttu-id="f1d19-118">Selezionare **Gestione articoli** \> **Impostazione** \> **Monitoraggio di magazzino** \> **Capacità di carico di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="f1d19-118">Select **Inventory management** \> **Setup** \> **Warehouse monitoring** \> **Workload capacity**.</span></span>
2. <span data-ttu-id="f1d19-119">Nel riquadro azioni selezionare **Nuova** per creare una nuova impostazione di capacità del carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="f1d19-119">On the Action Pane, select **New** to create a workload capacity setup.</span></span>
3. <span data-ttu-id="f1d19-120">Fare clic su **Nuovo** nella Scheda dettaglio **Magazzini**, quindi immettere i valori sulla riga per associare un magazzino all'impostazione di capacità del carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="f1d19-120">On the **Warehouses** FastTab, select **New**, and then enter values on the line to associate a warehouse with the workload capacity setup.</span></span>
4. <span data-ttu-id="f1d19-121">Selezionare la casella controllo **Carico di lavoro combinato in entrata e in uscita** se il report **Capacità di carico di lavoro** deve visualizzare il carico di lavoro totale delle transazioni in entrata e in uscita in una visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="f1d19-121">Select the **Combined inbound and outbound workload** check box if the **Workload capacity** report should show the total workload for incoming and outgoing transactions in one view.</span></span>
5. <span data-ttu-id="f1d19-122">Nella Scheda dettaglio **Tipi di transazione** selezionare i tipi di transazione in entrata e in uscita a cui si applicheranno i limiti del carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="f1d19-122">On the **Transaction types** FastTab, select the types of incoming and outgoing transactions that the workload limits will apply to.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f1d19-123">È necessario selezionare almeno un tipo di transazione sia per il carico di lavoro in ingresso che per quello in uscita.</span><span class="sxs-lookup"><span data-stu-id="f1d19-123">You must select at least one transaction type for both the incoming workload and the outgoing workload.</span></span>

#### <a name="define-limits-for-volume-or-weight"></a><span data-ttu-id="f1d19-124">Definizione dei limiti per volume o peso</span><span class="sxs-lookup"><span data-stu-id="f1d19-124">Define limits for volume or weight</span></span>

<span data-ttu-id="f1d19-125">È possibile impostare limiti per il volume o il peso a seconda di quale limitazione è rilevante per la forza lavoro di magazzino.</span><span class="sxs-lookup"><span data-stu-id="f1d19-125">You can set up limits for volume or weight, depending on the limitation that is relevant for the warehouse workforce.</span></span> <span data-ttu-id="f1d19-126">I limiti specificati vengono inclusi nella proiezione di capacità del carico di lavoro che è possibile visualizzare nel report **Capacità di carico di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="f1d19-126">The limits that you specify are included in the workload capacity projection that you can view on the **Workload capacity** report.</span></span>

<span data-ttu-id="f1d19-127">Per proiettare le informazioni relative a volume e peso degli articoli, il volume standard e il peso di un articolo di magazzino devono essere specificati per tutti i prodotti.</span><span class="sxs-lookup"><span data-stu-id="f1d19-127">To project information about volume and weight for items, the standard volume of one inventory item and the weight of one inventory item must be specified for all products.</span></span> <span data-ttu-id="f1d19-128">I campi obbligatori sono disponibili nei seguenti gruppi di campi nella Scheda dettaglio **Gestione articoli** della pagina **Dettagli prodotto rilasciato** :</span><span class="sxs-lookup"><span data-stu-id="f1d19-128">The fields that are required are available in the following field groups on the **Manage inventory** FastTab of the **Released product details** page:</span></span>

- <span data-ttu-id="f1d19-129">Movimentazione</span><span class="sxs-lookup"><span data-stu-id="f1d19-129">Handling</span></span>
- <span data-ttu-id="f1d19-130">Dimensioni fisiche</span><span class="sxs-lookup"><span data-stu-id="f1d19-130">Physical dimensions</span></span>
- <span data-ttu-id="f1d19-131">Misure peso</span><span class="sxs-lookup"><span data-stu-id="f1d19-131">Weight measurements</span></span>

<span data-ttu-id="f1d19-132">Se queste informazioni non sono state specificate correttamente, alla generazione del report **Capacità di carico di lavoro** si riceverà un messaggio.</span><span class="sxs-lookup"><span data-stu-id="f1d19-132">If this information isn't specified correctly, you receive a message when you generate the **Workload capacity** report.</span></span> <span data-ttu-id="f1d19-133">Dal report è quindi possibile effettuare il drill-down per identificare le informazioni mancanti necessarie per proiettare il carico di lavoro futuro.</span><span class="sxs-lookup"><span data-stu-id="f1d19-133">From the report, you can then drill down to identify the missing information that is required in order to project the future workload.</span></span>

### <a name="associate-a-workload-capacity-setup-with-a-master-plan"></a><span data-ttu-id="f1d19-134">Associare un'impostazione della capacità del carico di lavoro a un piano generale</span><span class="sxs-lookup"><span data-stu-id="f1d19-134">Associate a workload capacity setup with a master plan</span></span>

1. <span data-ttu-id="f1d19-135">Selezionare **Gestione articoli** \> **Periodico** \> **Programma carico di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="f1d19-135">Select **Inventory management** \> **Periodic** \> **Schedule workload**.</span></span>
2. <span data-ttu-id="f1d19-136">Nel campo **Piano generale** selezionare il piano generale da utilizzare per le proiezioni del carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="f1d19-136">In the **Master plan** field, select the master plan to use for workload projections.</span></span>
3. <span data-ttu-id="f1d19-137">Nel campo **Numero di giorni** specificare il numero di giorni coperti dalla proiezione del carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="f1d19-137">In the **Number of days** field, specify the number of days that the workload projection covers.</span></span>
4. <span data-ttu-id="f1d19-138">Nel campo **Carico di lavoro** selezionare l'impostazione del carico di lavoro da associare al piano generale.</span><span class="sxs-lookup"><span data-stu-id="f1d19-138">In the **Workload** field, select the workload setup to associate with the master plan.</span></span>

### <a name="view-workload-capacity"></a><span data-ttu-id="f1d19-139">Visualizzare la capacità del carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="f1d19-139">View workload capacity</span></span>

1. <span data-ttu-id="f1d19-140">Selezionare **Gestione inventario** \> **Richieste di informazioni e report** \> **Report inventario fisico** \> **Capacità di carico di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="f1d19-140">Select **Inventory management** \> **Inquiries and reports** \> **Physical inventory reports** \> **Workload capacity**.</span></span>
2. <span data-ttu-id="f1d19-141">Nel campo **Numero di colonne** specificare il numero delle colonne da visualizzare nel report.</span><span class="sxs-lookup"><span data-stu-id="f1d19-141">In the **Number of columns** field, specify the number of columns to show on the report.</span></span>
3. <span data-ttu-id="f1d19-142">Nel campo **Tipo di ordine**, selezionare **Pianificato e confermato**, **Pianificato** o **Confermato** per indicare il tipo di ordini da proiettare nel report.</span><span class="sxs-lookup"><span data-stu-id="f1d19-142">In the **Order type** field, select **Planned and confirmed**, **Planned**, or **Confirmed** to indicate the type of orders to project on the report.</span></span>
4. <span data-ttu-id="f1d19-143">Nel campo **Tipo di carico** selezionare un tipo di carico per indicare se la capacità del carico di lavoro deve essere proiettata per il volume o il peso.</span><span class="sxs-lookup"><span data-stu-id="f1d19-143">In the **Load type** field, select a load type to specify whether the workload capacity should be projected for volume or weight.</span></span>
5. <span data-ttu-id="f1d19-144">Nel campo **Capacità di carico di lavoro** selezionare un'impostazione di capacità del carico da lavoro.</span><span class="sxs-lookup"><span data-stu-id="f1d19-144">In the **Workload capacity** field, select a workload capacity setup.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]