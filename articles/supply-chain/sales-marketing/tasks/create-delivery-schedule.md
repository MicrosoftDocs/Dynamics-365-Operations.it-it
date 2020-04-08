---
title: Creare una programmazione consegna
description: Questa procedura dimostra come creare una programmazione consegna per un ordine cliente.
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesDeliverySchedule, SalesEditLines,  SrsReportViewerForm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 90ddb1f26dc3bf23fe5fc44281d74ed80f59e675
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3146557"
---
# <a name="create-delivery-schedule"></a><span data-ttu-id="98b84-103">Creare una programmazione consegna</span><span class="sxs-lookup"><span data-stu-id="98b84-103">Create delivery schedule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="98b84-104">Questa procedura dimostra come creare una programmazione consegna per un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="98b84-104">This procedure demonstrates how to create a delivery schedule for a sales order.</span></span> <span data-ttu-id="98b84-105">Una programmazione consegna viene utilizzata quando si richiede che una quantità di un ordine o di un'offerta venga consegnata in più spedizioni.</span><span class="sxs-lookup"><span data-stu-id="98b84-105">A delivery schedule is used when a quantity on an order or a quotation is requested to be delivered in multiple shipments.</span></span> <span data-ttu-id="98b84-106">È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure nei propri dati.</span><span class="sxs-lookup"><span data-stu-id="98b84-106">You can run this procedure in demo data company USMF or on your own data.</span></span>


## <a name="create-delivery-schedule"></a><span data-ttu-id="98b84-107">Creare una programmazione consegna</span><span class="sxs-lookup"><span data-stu-id="98b84-107">Create delivery schedule</span></span>
1. <span data-ttu-id="98b84-108">Fare clic su Tutti gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="98b84-108">Go to All sales orders.</span></span>
2. <span data-ttu-id="98b84-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="98b84-109">Click New.</span></span>
3. <span data-ttu-id="98b84-110">Nel campo Conto cliente, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="98b84-110">In the Customer account field, enter or select a value.</span></span>
4. <span data-ttu-id="98b84-111">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="98b84-111">Click OK.</span></span>
5. <span data-ttu-id="98b84-112">Nel campo Numero di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="98b84-112">In the Item number field, enter or select a value.</span></span>
6. <span data-ttu-id="98b84-113">Nel campo Quantità, immettere un numero maggiore di 1.</span><span class="sxs-lookup"><span data-stu-id="98b84-113">In the Quantity field, enter a number that is bigger than 1.</span></span>
7. <span data-ttu-id="98b84-114">Fare clic su Riga ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="98b84-114">Click Sales order line.</span></span>
8. <span data-ttu-id="98b84-115">Fare clic su Programmazione consegna.</span><span class="sxs-lookup"><span data-stu-id="98b84-115">Click Delivery schedule.</span></span>
    * <span data-ttu-id="98b84-116">La pagina Programmazione consegna è il luogo in cui è possibile specificare il numero di spedizioni in cui la quantità totale della riga ordine verrà consegnata al cliente.</span><span class="sxs-lookup"><span data-stu-id="98b84-116">The Delivery schedule page is the place where you can specify the number of shipments in which the total quantity of the order line will be delivered to the customer.</span></span>    
    * <span data-ttu-id="98b84-117">Per impostazione predefinita, il sistema copia la quantità totale e altri dettagli di consegna della riga di vendita originale nella prima riga di programmazione consegna.</span><span class="sxs-lookup"><span data-stu-id="98b84-117">By default, the system copies the total quantity and other delivery details of the original sales line into the first delivery schedule line.</span></span> <span data-ttu-id="98b84-118">In questo esempio creeremo una programmazione per due spedizioni, con uno scostamento della data della seconda spedizione di una settimana rispetto alla prima.</span><span class="sxs-lookup"><span data-stu-id="98b84-118">In this example, we'll create a schedule for two shipments, with the second shipment's date offset by a week from the first one.</span></span>  
9. <span data-ttu-id="98b84-119">Nel campo Quantità, immettere un numero appartenente alla quantità totale.</span><span class="sxs-lookup"><span data-stu-id="98b84-119">In the Quantity field, enter a number that is part of the total quantity.</span></span>
10. <span data-ttu-id="98b84-120">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="98b84-120">Click New.</span></span>
11. <span data-ttu-id="98b84-121">Nel campo Quantità immettere la quantità rimanente.</span><span class="sxs-lookup"><span data-stu-id="98b84-121">In the Quantity field, enter the remaining quantity.</span></span>
12. <span data-ttu-id="98b84-122">Nel campo Data di spedizione richiesta, immettere una data che sia una settimana dopo a partire dalla data della prima riga di consegna.</span><span class="sxs-lookup"><span data-stu-id="98b84-122">In the Requested ship date field, enter a date a date that is one week ahead from the date of the first delivery line.</span></span>
    * <span data-ttu-id="98b84-123">Le due opzioni della Scheda dettaglio Conversione spese controllano la modalità di distribuzione delle spese tra le righe di programmazione consegna, una volta assegnate alla riga ordine originale.</span><span class="sxs-lookup"><span data-stu-id="98b84-123">The two options on the Charges conversion FastTab control how you want the charges to be distributed across the delivery schedule lines, once they've been assigned to the original order line.</span></span> <span data-ttu-id="98b84-124">Se si seleziona Copia importi lordi, lo stesso importo di spesa viene copiato in ciascuna riga.</span><span class="sxs-lookup"><span data-stu-id="98b84-124">If you select Copy gross amounts, the same charge amount is copied to each line.</span></span> <span data-ttu-id="98b84-125">L'opzione Assegna a righe consegna divide equamente la spesa tra le righe consegna.</span><span class="sxs-lookup"><span data-stu-id="98b84-125">The Allocate to delivery lines option divides the charge equally across the delivery lines.</span></span>  
    * <span data-ttu-id="98b84-126">Solo le spese fisse possono essere divise, mentre quelle variabili vengono sempre copiate nelle righe.</span><span class="sxs-lookup"><span data-stu-id="98b84-126">Only fixed charges can be divided, whereas variable charges will still be copied to the lines.</span></span>  
13. <span data-ttu-id="98b84-127">Spostare il cursore lontano dalla seconda riga di consegna per aggiornare la pagina.</span><span class="sxs-lookup"><span data-stu-id="98b84-127">Move the cursor away from the second delivery line to update the page.</span></span>
    * <span data-ttu-id="98b84-128">È possibile tenere traccia della quantità totale che viene allocata alle righe di programmazione consegna guardando i campi Totale e Rimanente.</span><span class="sxs-lookup"><span data-stu-id="98b84-128">You can keep track of the total quantity that's allocated to the delivery schedule lines by looking at the Total and Remaining fields.</span></span> <span data-ttu-id="98b84-129">Se la quantità rimanente da zero, la quantità totale della riga originale è stata allocata alla programmazione.</span><span class="sxs-lookup"><span data-stu-id="98b84-129">When the remaining quantity is zero, the full quantity from the original line has been allocated to the schedule.</span></span>   
14. <span data-ttu-id="98b84-130">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="98b84-130">Click OK.</span></span>
    * <span data-ttu-id="98b84-131">La programmazione consegna ora è stata copiata nelle righe ordine.</span><span class="sxs-lookup"><span data-stu-id="98b84-131">The delivery schedule has now been copied to the order lines.</span></span>   
    * <span data-ttu-id="98b84-132">La riga ordine originale, denominata riga commerciale, è stata convertita in riga ordine con più consegne.</span><span class="sxs-lookup"><span data-stu-id="98b84-132">The original order line, referred to as a Commercial line, has been converted to an Order line with multiple deliveries.</span></span> <span data-ttu-id="98b84-133">È contrassegnata con un'icona distinta e funge da intestazione delle righe consegna.</span><span class="sxs-lookup"><span data-stu-id="98b84-133">It is marked with a distinct icon and acts as a header for the delivery lines.</span></span>  
    * <span data-ttu-id="98b84-134">Le due nuove righe, denominate righe consegna, costituiscono una programmazione consegna.</span><span class="sxs-lookup"><span data-stu-id="98b84-134">The two new lines, referred to as delivery lines, make up one delivery schedule.</span></span> <span data-ttu-id="98b84-135">L'ordine verrà elaborato rispetto a queste righe e non alla riga originale.</span><span class="sxs-lookup"><span data-stu-id="98b84-135">The order will be processed against these lines and not the original line.</span></span> <span data-ttu-id="98b84-136">Se i documenti ad esempio i documenti di conferma, le distinte di prelievo, i documenti di trasporto o le fatture vengono stampati, verranno visualizzate solo le righe consegna.</span><span class="sxs-lookup"><span data-stu-id="98b84-136">If documents such as confirmation slips, picking lists, packing slips, or invoices are printed, only the delivery lines are shown.</span></span>   
    * <span data-ttu-id="98b84-137">Le righe consegna possono avere date di consegna, quantità, modalità di consegna e dimensioni di immagazzinamento diverse, ad esempio sito e magazzino.</span><span class="sxs-lookup"><span data-stu-id="98b84-137">The delivery lines can have different delivery dates, quantities, modes of delivery, and storage dimensions, such as site and warehouse.</span></span> <span data-ttu-id="98b84-138">Tuttavia, le dimensioni prodotto devono corrispondere sempre a quelle nella riga commerciale e non possono essere modificate.</span><span class="sxs-lookup"><span data-stu-id="98b84-138">However, the product dimensions must always match the ones on the commercial line and can't be changed.</span></span>  
15. <span data-ttu-id="98b84-139">Nel campo Quantità, immettere un numero maggiore di quello corrente.</span><span class="sxs-lookup"><span data-stu-id="98b84-139">In the Quantity field, enter a number that's bigger than the current one.</span></span>
16. <span data-ttu-id="98b84-140">Selezionare la riga commerciale per visualizzare l'effetto del ricalcolo della quantità.</span><span class="sxs-lookup"><span data-stu-id="98b84-140">Select the commercial line to see the effect of the quantity recalculation.</span></span>
17. <span data-ttu-id="98b84-141">Nel riquadro azioni fare clic su Preleva e imballa.</span><span class="sxs-lookup"><span data-stu-id="98b84-141">On the Action Pane, click Pick and pack.</span></span>
18. <span data-ttu-id="98b84-142">Fare clic su Registra documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="98b84-142">Click Post packing slip.</span></span>
19. <span data-ttu-id="98b84-143">Espandere la sezione Parametri.</span><span class="sxs-lookup"><span data-stu-id="98b84-143">Expand the Parameters section.</span></span>
20. <span data-ttu-id="98b84-144">Nel campo Quantità selezionare "Tutto".</span><span class="sxs-lookup"><span data-stu-id="98b84-144">In the Quantity field, select 'All'.</span></span>
    * <span data-ttu-id="98b84-145">Si noti che il documento di trasporto verrà creato per le due righe di programmazione consegna e non per la riga ordine originale.</span><span class="sxs-lookup"><span data-stu-id="98b84-145">Note that the packing slip will be created for the two delivery schedule lines and not the original order line.</span></span>  
21. <span data-ttu-id="98b84-146">Selezionare Sì nel campo Stampa documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="98b84-146">Select Yes in the Print packing slip field.</span></span>
22. <span data-ttu-id="98b84-147">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="98b84-147">Click OK.</span></span>
23. <span data-ttu-id="98b84-148">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="98b84-148">Click Yes.</span></span>
24. <span data-ttu-id="98b84-149">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="98b84-149">Close the page.</span></span>

