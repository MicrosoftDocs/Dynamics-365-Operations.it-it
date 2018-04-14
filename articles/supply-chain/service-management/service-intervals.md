---
title: Intervalli assistenza
description: L'intervallo di assistenza indica la frequenza con cui vengono create righe di ordine di assistenza per le righe di contratto di assistenza in caso di creazione degli ordini di assistenza.
author: YuyuScheller
manager: AnnBe
ms.date: 02/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 1f21202c215f98213aae21a74fb91127a73ec609
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---

# <a name="service-intervals"></a><span data-ttu-id="dc5c5-103">Intervalli assistenza</span><span class="sxs-lookup"><span data-stu-id="dc5c5-103">Service intervals</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="dc5c5-104">L'intervallo del contratto di assistenza indica la frequenza con cui vengono create righe di ordine di assistenza per le righe di contratto di assistenza nel caso di creazione automatica degli ordini di assistenza.</span><span class="sxs-lookup"><span data-stu-id="dc5c5-104">The service agreement interval indicates the frequency with which service order lines are created for service agreement lines when you create service orders automatically.</span></span>

<span data-ttu-id="dc5c5-105">Quando gli ordini di assistenza vengono creati automaticamente, le righe di ordine di assistenza vengono create in base all'intervallo specificato per la riga di contratto di assistenza dalla data di inizio della riga di contratto.</span><span class="sxs-lookup"><span data-stu-id="dc5c5-105">When you create service orders automatically, service order lines are created according to the interval that you have specified for the service agreement line from the start date of the agreement line.</span></span>

<span data-ttu-id="dc5c5-106">Se il campo **Intervallo** di una riga di contratto di assistenza nella pagina **Contratti di assistenza** è vuoto, la riga rappresenta un evento occasionale e non viene utilizzata per creare ripetutamente ordini di assistenza.</span><span class="sxs-lookup"><span data-stu-id="dc5c5-106">If the **Interval** field of a service agreement line in the **Service agreements** page is blank, the line is a one-time event, and it is not used to create service orders repeatedly.</span></span>

## <a name="example"></a><span data-ttu-id="dc5c5-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="dc5c5-107">Example</span></span>

<span data-ttu-id="dc5c5-108">In questo esempio, viene illustrato il modo in cui un intervallo di assistenza influisce sulle righe di contratto di assistenza e sulle righe di ordine di assistenza in un ordine di assistenza.</span><span class="sxs-lookup"><span data-stu-id="dc5c5-108">This example illustrates how a service interval will affect service agreement lines and service order lines on a service order.</span></span>

### <a name="create-a-service-agreement"></a><span data-ttu-id="dc5c5-109">Creare un contratto di assistenza</span><span class="sxs-lookup"><span data-stu-id="dc5c5-109">Create a service agreement</span></span>

<span data-ttu-id="dc5c5-110">Innanzitutto, creare un contratto di assistenza e impostare l'opzione **Combina ordini di assistenza** su **In base al contratto di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="dc5c5-110">First, you create a service agreement and set the **Combine service orders** option to **By service agreement**.</span></span>

1. <span data-ttu-id="dc5c5-111">Fare clic su **Contratti di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="dc5c5-111">Click **Service agreements**</span></span>
2. <span data-ttu-id="dc5c5-112">Nel **riquadro azioni**, nel gruppo **Nuovo** della scheda **Contratto di assistenza** fare clic su **Contratto di assistenza** per creare un nuovo contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="dc5c5-112">On the **Action Pane**, on the **Service agreement** tab, in the **New** group, click **Service agreement** to create a new service agreement.</span></span>
3. <span data-ttu-id="dc5c5-113">Immettere una descrizione, selezionare un progetto nel campo **ID progetto** e immettere una data nel campo **Data di inizio**.</span><span class="sxs-lookup"><span data-stu-id="dc5c5-113">Enter a description, select a project in the **Project ID** field, and enter a date in the **Start date** field.</span></span>
4. <span data-ttu-id="dc5c5-114">Nel campo **Combina ordini di assistenza** selezionare **In base al contratto di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="dc5c5-114">In the **Combine service orders** field, select **By service agreement**.</span></span>

<span data-ttu-id="dc5c5-115">È stato così creato il seguente contratto di assistenza:</span><span class="sxs-lookup"><span data-stu-id="dc5c5-115">You have now created the following service agreement:</span></span>

| <span data-ttu-id="dc5c5-116">Project</span><span class="sxs-lookup"><span data-stu-id="dc5c5-116">Project</span></span>      | <span data-ttu-id="dc5c5-117">Data di inizio</span><span class="sxs-lookup"><span data-stu-id="dc5c5-117">Start date</span></span>                                                                         |
|--------------|------------------------------------------------------------------------------------|
| <span data-ttu-id="dc5c5-118">Progetto selezionato</span><span class="sxs-lookup"><span data-stu-id="dc5c5-118">Your project</span></span> | <span data-ttu-id="dc5c5-119">La data specificata per il progetto.</span><span class="sxs-lookup"><span data-stu-id="dc5c5-119">The date you specified for the project.</span></span> <span data-ttu-id="dc5c5-120">In questo esempio viene utilizzata la data corrente.</span><span class="sxs-lookup"><span data-stu-id="dc5c5-120">In this example, the current date is used.</span></span> |

### <a name="create-a-service-agreement-line"></a><span data-ttu-id="dc5c5-121">Creare una riga di contratto di assistenza</span><span class="sxs-lookup"><span data-stu-id="dc5c5-121">Create a service agreement line</span></span>

<span data-ttu-id="dc5c5-122">Creare successivamente una riga di contratto di assistenza con **Ora** come tipo di transazione.</span><span class="sxs-lookup"><span data-stu-id="dc5c5-122">Next, you create a service agreement line that has the transaction type **Hour**.</span></span>

<span data-ttu-id="dc5c5-123">Per completare questa parte dell'esempio, è necessario creare un intervallo di assistenza di 10 giorni nella pagina **Intervalli assistenza**.</span><span class="sxs-lookup"><span data-stu-id="dc5c5-123">To complete this part of the example, you must create a service interval of 10 days in the **Service intervals** page.</span></span> 

1. <span data-ttu-id="dc5c5-124">Selezionare il contratto di assistenza appena creato.</span><span class="sxs-lookup"><span data-stu-id="dc5c5-124">Select the service agreement that you just created.</span></span> 
2. <span data-ttu-id="dc5c5-125">Nella scheda dettaglio **Righe** fare clic sul pulsante **Aggiungi** per creare una nuova riga nel riquadro inferiore della pagina **Contratti di assistenza** .</span><span class="sxs-lookup"><span data-stu-id="dc5c5-125">On the **Lines** FastTab, click the **Add** button to create a new line in the lower pane of the **Service agreements** page.</span></span>
3. <span data-ttu-id="dc5c5-126">Nel campo **Tipo di transazione** selezionare **Ora**.</span><span class="sxs-lookup"><span data-stu-id="dc5c5-126">In the **Transaction type** field, select **Hour**.</span></span>
4. <span data-ttu-id="dc5c5-127">Nel campo **Lavoratore** selezionare il lavoratore che fornirà il servizio.</span><span class="sxs-lookup"><span data-stu-id="dc5c5-127">In the **Worker** field, select the worker who will deliver the service.</span></span>
5. <span data-ttu-id="dc5c5-128">Nel campo **Intervallo di assistenza** selezionare l'intervallo di 10 giorni.</span><span class="sxs-lookup"><span data-stu-id="dc5c5-128">In the **Service interval** field, select the 10 days interval.</span></span>

<span data-ttu-id="dc5c5-129">È stata così creata una riga di contratto di assistenza con le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="dc5c5-129">You have now created a service agreement line with the following information:</span></span>

| <span data-ttu-id="dc5c5-130">Tipo di transazione</span><span class="sxs-lookup"><span data-stu-id="dc5c5-130">Transaction type</span></span> | <span data-ttu-id="dc5c5-131">Data di inizio</span><span class="sxs-lookup"><span data-stu-id="dc5c5-131">Start date</span></span>                               | <span data-ttu-id="dc5c5-132">Intervallo di assistenza</span><span class="sxs-lookup"><span data-stu-id="dc5c5-132">Service interval</span></span> |
|------------------|------------------------------------------|------------------|
| <span data-ttu-id="dc5c5-133">Ore</span><span class="sxs-lookup"><span data-stu-id="dc5c5-133">Hour</span></span>             | <span data-ttu-id="dc5c5-134">Data corrente.</span><span class="sxs-lookup"><span data-stu-id="dc5c5-134">The current date.</span></span>                        | <span data-ttu-id="dc5c5-135">Ogni 10 giorni</span><span class="sxs-lookup"><span data-stu-id="dc5c5-135">Every 10 days</span></span>    |
| <span data-ttu-id="dc5c5-136">Lavoro</span><span class="sxs-lookup"><span data-stu-id="dc5c5-136">Worker</span></span>           | <span data-ttu-id="dc5c5-137">Il lavoratore che fornirà il servizio.</span><span class="sxs-lookup"><span data-stu-id="dc5c5-137">The worker who will perform the service.</span></span> |                  |

<span data-ttu-id="dc5c5-138">Per la riga non è stato specificato un intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="dc5c5-138">There is no time window specified for the line.</span></span> 

### <a name="create-planned-service-orders"></a><span data-ttu-id="dc5c5-139">Creare ordini di assistenza pianificati</span><span class="sxs-lookup"><span data-stu-id="dc5c5-139">Create planned service orders</span></span>

<span data-ttu-id="dc5c5-140">È possibile creare ora gli ordini di assistenza pianificati e le righe di ordine di assistenza per il mese prossimo.</span><span class="sxs-lookup"><span data-stu-id="dc5c5-140">You can now create planned service orders and service order lines for the coming month.</span></span>

1. <span data-ttu-id="dc5c5-141">Nella pagina **Contratti di assistenza**, nel **Riquadro azioni** della scheda **Fornisci**, fare clic su **Ordini di assistenza pianificati**.</span><span class="sxs-lookup"><span data-stu-id="dc5c5-141">In the **Service agreements** page, on the **Action Pane**, on the **Deliver** tab, click **Planned service orders**.</span></span>
2. <span data-ttu-id="dc5c5-142">Nella pagina **Crea ordini di assistenza** immettere la data corrente nel campo **Dal** e la data che corrisponde a un mese a partire dalla data corrente nel campo **Al**.</span><span class="sxs-lookup"><span data-stu-id="dc5c5-142">In the **Create service orders** page, enter the current date in the **From date** field and a date that is one month from the current date in the **To date** field.</span></span>
3. <span data-ttu-id="dc5c5-143">Impostare il dispositivo di scorrimento **Ora** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="dc5c5-143">Set the **Hour** slider to **Yes**.</span></span> 
4. <span data-ttu-id="dc5c5-144">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc5c5-144">Click **OK**.</span></span>

<span data-ttu-id="dc5c5-145">Poiché non è presente un raggruppamento nell'ordine di assistenza, definito dall'opzione **In base al contratto di assistenza** nel campo **Combina ordini di assistenza**, viene creata una riga di ordine di assistenza per ogni ordine di assistenza.</span><span class="sxs-lookup"><span data-stu-id="dc5c5-145">Because there is no grouping on the service order (defined by the **By service agreement** option in the **Combine service orders** field), one service order line is created per service order.</span></span>

### <a name="service-orders-created"></a><span data-ttu-id="dc5c5-146">Ordini di assistenza creati</span><span class="sxs-lookup"><span data-stu-id="dc5c5-146">Service orders created</span></span>

<span data-ttu-id="dc5c5-147">Sono state create tre righe di ordine di assistenza nell'intervallo di tempo specificato nella finestra di dialogo **Crea ordini di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="dc5c5-147">Three service order lines have been created within the time frame that you specified in the **Create service orders** dialog box.</span></span> <span data-ttu-id="dc5c5-148">È possibile visualizzare le righe di assistenza nella pagina **Contratti di assistenza** (**riquadro azioni** \> scheda **Fornisci** \>pulsante **Visualizza**).</span><span class="sxs-lookup"><span data-stu-id="dc5c5-148">You can view the service order lines in the **Service agreements** page (**Action Pane** \> **Deliver** tab \>**View** button).</span></span>

## <a name="related-topics"></a><span data-ttu-id="dc5c5-149">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="dc5c5-149">Related topics</span></span>

[<span data-ttu-id="dc5c5-150">Impostare gli intervalli di assistenza</span><span class="sxs-lookup"><span data-stu-id="dc5c5-150">Set up service intervals</span></span>](set-up-service-intervals.md)  


