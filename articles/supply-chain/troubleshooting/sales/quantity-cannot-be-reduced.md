---
title: Impossibile ridurre la quantità quando un ordine cliente viene annullato
description: Impossibile ridurre la quantità quando un ordine cliente viene annullato.
author: hja-ms
ms.date: 5/17/2021
ms.topic: troubleshooting
ms.search.form: SalesTable_SalesCancelOrder, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: hja
ms.search.validFrom: 2021-05-17
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 1a2cc9c9fd3d085508fc652bc9ee0a352d869dee
ms.sourcegitcommit: a02d3d64c899f8554b74342d5a1856d824bf1abe
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2021
ms.locfileid: "6230838"
---
# <a name="the-quantity-cant-be-reduced-when-a-sales-order-is-canceled"></a><span data-ttu-id="1380a-103">Impossibile ridurre la quantità quando un ordine cliente viene annullato</span><span class="sxs-lookup"><span data-stu-id="1380a-103">The quantity can't be reduced when a sales order is canceled</span></span>

<span data-ttu-id="1380a-104">Codice errore: SYS138831</span><span class="sxs-lookup"><span data-stu-id="1380a-104">Error code: SYS138831</span></span>

## <a name="symptoms"></a><span data-ttu-id="1380a-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="1380a-105">Symptoms</span></span>

<span data-ttu-id="1380a-106">Il sistema mostra il seguente messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="1380a-106">The system shows the following error message:</span></span>

> <span data-ttu-id="1380a-107">La quantità non può essere ridotta.</span><span class="sxs-lookup"><span data-stu-id="1380a-107">The quantity cannot be reduced.</span></span> <span data-ttu-id="1380a-108">Il numero di transazioni di inventario nell'ordine è troppo basso perché la quantità o parte di essa sia referenziata da un ordine di output o da un ordine di produzione oppure è contrassegnata a fronte di altre transazioni.</span><span class="sxs-lookup"><span data-stu-id="1380a-108">The number of inventory transactions on order is too low because the quantity or part of it is referenced by an output order or a production order or is marked against other transactions.</span></span>

## <a name="cause"></a><span data-ttu-id="1380a-109">Causa</span><span class="sxs-lookup"><span data-stu-id="1380a-109">Cause</span></span>

<span data-ttu-id="1380a-110">Se il lavoro è associato a un ordine cliente, non è possibile annullare l'ordine cliente finché il lavoro non viene annullato e stornato.</span><span class="sxs-lookup"><span data-stu-id="1380a-110">If work is associated with a sales order, you can't cancel the sales order until the work is canceled and reversed.</span></span> <span data-ttu-id="1380a-111">Questo requisito si applica anche se il lavoro associato all'ordine cliente viene chiuso.</span><span class="sxs-lookup"><span data-stu-id="1380a-111">This requirement applies even if the work that is associated with the sales order is closed.</span></span>

## <a name="resolution"></a><span data-ttu-id="1380a-112">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="1380a-112">Resolution</span></span>

<span data-ttu-id="1380a-113">Per risolvere il problema, completare le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="1380a-113">To fix this issue, complete the following tasks:</span></span>

1. <span data-ttu-id="1380a-114">Annullare il lavoro aperto.</span><span class="sxs-lookup"><span data-stu-id="1380a-114">Cancel open work.</span></span>
1. <span data-ttu-id="1380a-115">Eliminare il carico.</span><span class="sxs-lookup"><span data-stu-id="1380a-115">Delete the load.</span></span>
1. <span data-ttu-id="1380a-116">Ridurre la quantità prelevata.</span><span class="sxs-lookup"><span data-stu-id="1380a-116">Reduce the picked quantity.</span></span>

### <a name="cancel-open-work"></a><span data-ttu-id="1380a-117">Annullare il lavoro aperto</span><span class="sxs-lookup"><span data-stu-id="1380a-117">Cancel open work</span></span>

<span data-ttu-id="1380a-118">Per annullare il lavoro aperto, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="1380a-118">To cancel open work, follow these steps.</span></span>

1. <span data-ttu-id="1380a-119">Vai a **Gestione magazzino \> Attività periodiche \> Pulitura \> Annulla lavoro**.</span><span class="sxs-lookup"><span data-stu-id="1380a-119">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="1380a-120">Nel campo **ID lavoro**, specifica l'ID del lavoro che desideri annullare e che attualmente ha valore **Stato lavoro** uguale a *Aperto*, *In corso*, *Annullato*, *Combinato* o *Chiuso*.</span><span class="sxs-lookup"><span data-stu-id="1380a-120">In the **Work ID** field, specify the ID of the work that you want to cancel, and that currently has a **Work status** value of *Open*, *In progress*, *Canceled*, *Combined*, or *Closed*.</span></span>
1. <span data-ttu-id="1380a-121">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="1380a-121">Select **OK**.</span></span>
1. <span data-ttu-id="1380a-122">Seleziona **Sì** per confermare che desideri annullare il lavoro.</span><span class="sxs-lookup"><span data-stu-id="1380a-122">Select **Yes** to confirm that you want to cancel the work.</span></span>

### <a name="delete-the-load"></a><span data-ttu-id="1380a-123">Eliminare il carico</span><span class="sxs-lookup"><span data-stu-id="1380a-123">Delete the load</span></span>

<span data-ttu-id="1380a-124">Per eliminare un carico, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="1380a-124">To delete a load, follow these steps.</span></span>

1. <span data-ttu-id="1380a-125">Seleziona **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="1380a-125">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="1380a-126">Apri l'ordine cliente rilevante.</span><span class="sxs-lookup"><span data-stu-id="1380a-126">Open the relevant sales order.</span></span>
1. <span data-ttu-id="1380a-127">Nella scheda dettaglio **Righe ordine cliente**, seleziona **Magazzino \> Dettagli lavoro**.</span><span class="sxs-lookup"><span data-stu-id="1380a-127">On the **Sales order lines** FastTab, select **Warehouse \> Work details**.</span></span>
1. <span data-ttu-id="1380a-128">Nel riquadro delle azioni della pagina **Lavoro**, nella scheda **Lavoro** del gruppo **Lavoro**, seleziona **Annulla lavoro**.</span><span class="sxs-lookup"><span data-stu-id="1380a-128">On the **Work** page, on the Action Pane, on the **Work** tab, in the **Work** group, select **Cancel work**.</span></span>
1. <span data-ttu-id="1380a-129">Conferma che il campo **Stato lavoro** sia impostato su *Annullato*.</span><span class="sxs-lookup"><span data-stu-id="1380a-129">Confirm that the **Work status** field is set to *Canceled*.</span></span>
1. <span data-ttu-id="1380a-130">Chiudi la pagina **Lavoro**.</span><span class="sxs-lookup"><span data-stu-id="1380a-130">Close the **Work** page.</span></span>
1. <span data-ttu-id="1380a-131">Nella pagina dei dettagli dell'ordine cliente, scheda dettaglio **Righe ordine cliente**, seleziona **Magazzino \> Dettagli carico**.</span><span class="sxs-lookup"><span data-stu-id="1380a-131">On the sales order details page, on the **Sales order lines** FastTab, select **Warehouse \> Load details**.</span></span>
1. <span data-ttu-id="1380a-132">Nel riquadro delle azioni seleziona **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="1380a-132">On the Action Pane, select **Delete**.</span></span>
1. <span data-ttu-id="1380a-133">Seleziona **Sì** per confermare che desideri eliminare il carico.</span><span class="sxs-lookup"><span data-stu-id="1380a-133">Select **Yes** to confirm that you want to delete the load.</span></span>
1. <span data-ttu-id="1380a-134">Chiudi la pagina **Carico**.</span><span class="sxs-lookup"><span data-stu-id="1380a-134">Close the **Load** page.</span></span>

### <a name="reduce-the-picked-quantity"></a><span data-ttu-id="1380a-135">Ridurre la quantità prelevata</span><span class="sxs-lookup"><span data-stu-id="1380a-135">Reduce the picked quantity</span></span>

<span data-ttu-id="1380a-136">Dopo che tutto il lavoro è stato annullato, segui questi passaggi per ridurre la quantità prelevata.</span><span class="sxs-lookup"><span data-stu-id="1380a-136">After all work has been canceled, follow these steps to reduce the picked quantity.</span></span>

1. <span data-ttu-id="1380a-137">Seleziona **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="1380a-137">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="1380a-138">Apri l'ordine cliente rilevante.</span><span class="sxs-lookup"><span data-stu-id="1380a-138">Open the relevant sales order.</span></span>
1. <span data-ttu-id="1380a-139">Nella scheda dettaglio **Righe ordine cliente**, seleziona **Aggiorna riga \> Prelievo** dalla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="1380a-139">On the **Sales order lines** FastTab, select **Update line \> Pick** from the toolbar.</span></span>
1. <span data-ttu-id="1380a-140">Nella pagina **Prelievo**, sezione **Transazioni**, seleziona la riga in cui il campo **Stato uscita** è impostato su *Prelevato*.</span><span class="sxs-lookup"><span data-stu-id="1380a-140">On the **Pick** page, in the **Transactions** section, select the line where the **Issue status** field is set to *Picked*.</span></span>
1. <span data-ttu-id="1380a-141">Nella sezione **Transazioni**, seleziona **Aggiungi riga di prelievo** dalla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="1380a-141">In the **Transactions** section, select **Add picking line** from the toolbar.</span></span>
1. <span data-ttu-id="1380a-142">Nella sezione **Righe di prelievo**, seleziona **Conferma Preleva tutto** dalla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="1380a-142">In the **Picking lines** section, select **Confirm pick all** from the toolbar.</span></span>
1. <span data-ttu-id="1380a-143">Chiudi la pagina **Prelievo**.</span><span class="sxs-lookup"><span data-stu-id="1380a-143">Close the **Pick** page.</span></span>
1. <span data-ttu-id="1380a-144">Nel riquadro delle azioni della pagina dei dettagli dell'ordine cliente, nella scheda **Ordine cliente**, gruppo **Conserva**, seleziona **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="1380a-144">On the sales order details page, on the Action Pane, on the **Sales order** tab, in the **Maintain** group, select **Cancel**.</span></span>
1. <span data-ttu-id="1380a-145">Seleziona **Sì** per confermare che desideri annullare l'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="1380a-145">Select **Yes** to confirm that you want to cancel the sales order.</span></span>
