--- 
title: Pegging di produzione snella da ordini cliente
description: "La procedura riguarda la convalida della struttura di pegging da una riga di vendita in cui l'articolo è prodotto con kanban."
author: ChristianRytt
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: dbab5ade75aa8999f7e91c5d27f896242f6c7604
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---
# <a name="lean-pegging-from-sales-orders"></a><span data-ttu-id="c009d-103">Pegging di produzione snella da ordini cliente</span><span class="sxs-lookup"><span data-stu-id="c009d-103">Lean pegging from sales orders</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c009d-104">La procedura riguarda la convalida della struttura di pegging da una riga di vendita in cui l'articolo è prodotto con kanban.</span><span class="sxs-lookup"><span data-stu-id="c009d-104">This procedure focuses on validating the pegging tree from a sales line where the item is produced with kanbans.</span></span> <span data-ttu-id="c009d-105">Dopo la convalida della struttura di pegging, tutti i processi kanban sono pianificati.</span><span class="sxs-lookup"><span data-stu-id="c009d-105">After validating the pegging tree, all the kanban jobs are planned.</span></span> <span data-ttu-id="c009d-106">Questa opzione è utile per scenari in cui l'incaricato dell'ordine cliente deve verificare che la produzione possa iniziare subito.</span><span class="sxs-lookup"><span data-stu-id="c009d-106">This is useful for order scenarios where the order taker needs to ensure that production can start right away.</span></span> <span data-ttu-id="c009d-107">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="c009d-107">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="c009d-108">Questa procedura è destinata per l'incaricato dell'ordine cliente avanzato che opera una società di produzione snella.</span><span class="sxs-lookup"><span data-stu-id="c009d-108">This procedure is intended for the advanced order taker working in a lean company.</span></span>


## <a name="create-a-sales-order-for-a-kanban-controlled-item"></a><span data-ttu-id="c009d-109">Creare un ordine cliente per un articolo controllato da kanban</span><span class="sxs-lookup"><span data-stu-id="c009d-109">Create a sales order for a kanban controlled item</span></span>
1. <span data-ttu-id="c009d-110">Fare clic su Tutti gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="c009d-110">Go to All sales orders.</span></span>
2. <span data-ttu-id="c009d-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="c009d-111">Click New.</span></span>
3. <span data-ttu-id="c009d-112">Nel campo Conto cliente, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c009d-112">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="c009d-113">Utilizzare US-001.</span><span class="sxs-lookup"><span data-stu-id="c009d-113">Use US-001.</span></span>  
4. <span data-ttu-id="c009d-114">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c009d-114">Click OK.</span></span>
5. <span data-ttu-id="c009d-115">Nel campo Numero articolo digitare "L0001".</span><span class="sxs-lookup"><span data-stu-id="c009d-115">In the Item number field, type 'L0001'.</span></span>
6. <span data-ttu-id="c009d-116">Impostare la quantità su "30".</span><span class="sxs-lookup"><span data-stu-id="c009d-116">Set Quantity to '30'.</span></span>
    * <span data-ttu-id="c009d-117">È importante che la quantità sia superiore a 24 per attivare la regola kanban di evento.</span><span class="sxs-lookup"><span data-stu-id="c009d-117">It is important that the quantity is higher than 24 in order to trigger the event kanban rule.</span></span>  

## <a name="open-a-pegging-tree"></a><span data-ttu-id="c009d-118">Aprire una struttura di pegging</span><span class="sxs-lookup"><span data-stu-id="c009d-118">Open a pegging tree</span></span> 
1. <span data-ttu-id="c009d-119">Fare clic su Prodotto e fornitura.</span><span class="sxs-lookup"><span data-stu-id="c009d-119">Click Product and supply.</span></span>
2. <span data-ttu-id="c009d-120">Fare clic su Visualizza struttura di pegging.</span><span class="sxs-lookup"><span data-stu-id="c009d-120">Click View pegging tree.</span></span>
    * <span data-ttu-id="c009d-121">Si noti che la struttura di pegging mostra tutti i livelli di pegging necessari per la riga ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="c009d-121">Notice that the pegging tree shows all levels of the pegging needed for the sales order line.</span></span> <span data-ttu-id="c009d-122">In questo caso, sono disponibili due livelli kanban e tutti i componenti richiesti.</span><span class="sxs-lookup"><span data-stu-id="c009d-122">In this case, there are two levels of kanbans and all the required components.</span></span>  

## <a name="plan-the-pegging-tree"></a><span data-ttu-id="c009d-123">Pianificare la struttura di pegging</span><span class="sxs-lookup"><span data-stu-id="c009d-123">Plan the pegging tree</span></span>
1. <span data-ttu-id="c009d-124">Nella struttura, selezionare 'Riga di vendita 000832\Kanban 000558'.</span><span class="sxs-lookup"><span data-stu-id="c009d-124">In the tree, select 'Sales line 000832\Kanban 000558'.</span></span>
2. <span data-ttu-id="c009d-125">Espandere la sezione Processi kanban.</span><span class="sxs-lookup"><span data-stu-id="c009d-125">Expand the Kanban jobs section.</span></span>
    * <span data-ttu-id="c009d-126">Si noti che lo stato del processo per il processo kanban è Non pianificato.</span><span class="sxs-lookup"><span data-stu-id="c009d-126">Notice that the job status for the kanban job is Not planned.</span></span>  
3. <span data-ttu-id="c009d-127">Fare clic su Pianifica intera struttura di pegging.</span><span class="sxs-lookup"><span data-stu-id="c009d-127">Click Plan entire pegging tree.</span></span>
    * <span data-ttu-id="c009d-128">In tal modo tutti i processi kanban vengono pianificati nella struttura di pegging, modificando lo stato del processo da Non pianificato a Pianificato.</span><span class="sxs-lookup"><span data-stu-id="c009d-128">This will plan all kanban jobs in the pegging tree, changing the Job status from Not planned to Planned.</span></span>  
4. <span data-ttu-id="c009d-129">Aggiorna la pagina.</span><span class="sxs-lookup"><span data-stu-id="c009d-129">Refresh the page.</span></span>
    * <span data-ttu-id="c009d-130">Si noti che lo stato del processo kanban è cambiato da Non pianificato a Pianificato.</span><span class="sxs-lookup"><span data-stu-id="c009d-130">Notice that the kanban Job status changed from Not planned to Planned.</span></span>  
5. <span data-ttu-id="c009d-131">Nella struttura, selezionare 'Riga di vendita 000832\Kanban 000558\Uscita per L0001\Kanban 000559'.</span><span class="sxs-lookup"><span data-stu-id="c009d-131">In the tree, select 'Sales line 000832\Kanban 000558\Issue for L0001\Kanban 000559'.</span></span>
    * <span data-ttu-id="c009d-132">Anche il processo per il secondo kanban viene pianificato perché l'intera struttura di pegging è pianificata.</span><span class="sxs-lookup"><span data-stu-id="c009d-132">The job for the second kanban is also planned, because the entire pegging tree is planned.</span></span> <span data-ttu-id="c009d-133">Si noti che lo stato del processo kanban è cambiato da Non pianificato a Pianificato.</span><span class="sxs-lookup"><span data-stu-id="c009d-133">Notice that the kanban job status is changed from Not planned to Planned.</span></span>  


