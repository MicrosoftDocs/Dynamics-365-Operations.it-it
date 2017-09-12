--- 
title: Creare un ordine fornitore con una programmazione consegna
description: Questa procedura dimostra come creare una programmazione consegna per un ordine foritore.
author: FrankDahl
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 1e4a0204d74c8966cd90b52ae13c88e222ebc3ef
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-purchase-order-with-a-delivery-schedule"></a><span data-ttu-id="d9567-103">Creare un ordine fornitore con una programmazione consegna</span><span class="sxs-lookup"><span data-stu-id="d9567-103">Create a purchase order with a delivery schedule</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d9567-104">Questa procedura dimostra come creare una programmazione consegna per un ordine foritore.</span><span class="sxs-lookup"><span data-stu-id="d9567-104">This procedure demonstrates how to create a delivery schedule for a purchase order.</span></span> <span data-ttu-id="d9567-105">Una programmazione consegna viene utilizzata quando si richiede che una quantità di un ordine o su un giornale di registrazione venga consegnata in più spedizioni.</span><span class="sxs-lookup"><span data-stu-id="d9567-105">A delivery schedule is used when a quantity on an order or a journal is requested to be delivered in multiple shipments.</span></span> <span data-ttu-id="d9567-106">L'esempio indicato in questa guida può essere utilizzato nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="d9567-106">The example shown in this guide can be used in the USMF demo data company.</span></span> <span data-ttu-id="d9567-107">Questa procedura viene in genere eseguita da un addetto agli acquisti.</span><span class="sxs-lookup"><span data-stu-id="d9567-107">This procedure would typically be done by a purchasing agent.</span></span>


## <a name="create-a-delivery-schedule"></a><span data-ttu-id="d9567-108">Creare una programmazione consegna</span><span class="sxs-lookup"><span data-stu-id="d9567-108">Create a delivery schedule</span></span>
1. <span data-ttu-id="d9567-109">Andare ad Approvvigionamento > Ordini fornitore> Tutti gli ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="d9567-109">Go to Procurement and sourcing > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="d9567-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="d9567-110">Click New.</span></span>
3. <span data-ttu-id="d9567-111">Digitare US-101 nel campo Conto fornitore.</span><span class="sxs-lookup"><span data-stu-id="d9567-111">In the Vendor account field, enter US-101.</span></span>
4. <span data-ttu-id="d9567-112">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="d9567-112">Click OK.</span></span>
5. <span data-ttu-id="d9567-113">Nel campo Numero articolo immettere M0001.</span><span class="sxs-lookup"><span data-stu-id="d9567-113">In the Item number field, enter M0001.</span></span>
6. <span data-ttu-id="d9567-114">Nel campo Quantità immettere 10.</span><span class="sxs-lookup"><span data-stu-id="d9567-114">In the Quantity field, enter 10.</span></span>
7. <span data-ttu-id="d9567-115">Fare clic su Riga ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="d9567-115">Click Purchase order line.</span></span>
8. <span data-ttu-id="d9567-116">Fare clic su Programmazione consegna.</span><span class="sxs-lookup"><span data-stu-id="d9567-116">Click Delivery schedule.</span></span>
    * <span data-ttu-id="d9567-117">La pagina Programmazione consegna è il luogo in cui è possibile specificare il numero di spedizioni in cui la quantità totale della riga ordine verrà consegnata dal fornitore.</span><span class="sxs-lookup"><span data-stu-id="d9567-117">The Delivery schedule page allows you to specify the number of shipments in which the total quantity of the order line will be delivered from the vendor.</span></span>  
    * <span data-ttu-id="d9567-118">Per impostazione predefinita, il sistema copia la quantità totale e altri dettagli di consegna della riga di acquisto originale nella prima riga di programmazione consegna.</span><span class="sxs-lookup"><span data-stu-id="d9567-118">By default, the system copies the total quantity and other delivery details of the original purchase line into the first delivery schedule line.</span></span> <span data-ttu-id="d9567-119">In questo esempio creeremo una programmazione per due spedizioni, con uno scostamento della data della seconda spedizione di una settimana rispetto alla prima.</span><span class="sxs-lookup"><span data-stu-id="d9567-119">In this example, we’ll create a schedule for two shipments, with the second shipment’s date offset by a week from the first shipment.</span></span>  
9. <span data-ttu-id="d9567-120">Nel campo Quantità modificare la quantità in 4.</span><span class="sxs-lookup"><span data-stu-id="d9567-120">In the Quantity field, change the quantity to 4.</span></span>
10. <span data-ttu-id="d9567-121">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="d9567-121">Click New.</span></span>
11. <span data-ttu-id="d9567-122">Nel campo Quantità immettere 6 come quantità rimanente.</span><span class="sxs-lookup"><span data-stu-id="d9567-122">In the Quantity field, enter 6 as the remaining quantity.</span></span>
    * <span data-ttu-id="d9567-123">Nel campo della data di consegna, selezionare una data che è di una settimana successiva alla prima riga di consegna.</span><span class="sxs-lookup"><span data-stu-id="d9567-123">In the delivery date field, select a date that’s one week after the date on the first delivery line.</span></span>  
    * <span data-ttu-id="d9567-124">È possibile tenere traccia della quantità totale che viene allocata alle righe di programmazione consegna guardando i campi Totale e Rimanente.</span><span class="sxs-lookup"><span data-stu-id="d9567-124">You can keep track of the total quantity that’s allocated to the delivery schedule lines by looking at the Total and Remaining fields.</span></span> <span data-ttu-id="d9567-125">Se la quantità rimanente da zero, la quantità totale della riga originale è stata allocata alla programmazione.</span><span class="sxs-lookup"><span data-stu-id="d9567-125">When the remaining quantity is zero, the full quantity from the original line has been allocated to the schedule.</span></span>  
12. <span data-ttu-id="d9567-126">Espandere la sezione Conversione spese.</span><span class="sxs-lookup"><span data-stu-id="d9567-126">Expand the Charges conversion section.</span></span>
    * <span data-ttu-id="d9567-127">Le opzioni qui permettono di determinare la distribuzione delle spese tra le righe della programmazione consegna.</span><span class="sxs-lookup"><span data-stu-id="d9567-127">The options here allow you to control how you want charges to be distributed across the delivery schedule lines.</span></span> <span data-ttu-id="d9567-128">Se si seleziona Copia importi lordi, lo stesso importo di spesa della riga ordine originale viene copiato in ciascuna riga di consegna.</span><span class="sxs-lookup"><span data-stu-id="d9567-128">If you select Copy gross amounts, the charge amount on the original order line is copied to each delivery line.</span></span> <span data-ttu-id="d9567-129">L'opzione Assegna a righe consegna divide le spese dalla riga originale secondo la quantità su ogni riga di consegna.</span><span class="sxs-lookup"><span data-stu-id="d9567-129">The Allocate to delivery lines option divides the original line charge according to the quantity on each delivery line.</span></span>  
13. <span data-ttu-id="d9567-130">Comprimere la sezione Conversione spese.</span><span class="sxs-lookup"><span data-stu-id="d9567-130">Collapse the Charges conversion section.</span></span>
14. <span data-ttu-id="d9567-131">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="d9567-131">Click OK.</span></span>
    * <span data-ttu-id="d9567-132">La programmazione consegna ora è stata applicata all'ordine.</span><span class="sxs-lookup"><span data-stu-id="d9567-132">The delivery schedule has now been applied to the order.</span></span>  
    * <span data-ttu-id="d9567-133">La riga ordine originale, ora denominata riga commerciale, è stata convertita in riga ordine con più consegne.</span><span class="sxs-lookup"><span data-stu-id="d9567-133">The original order line, now referred to as a Commercial line, has been converted to an Order line with multiple deliveries.</span></span> <span data-ttu-id="d9567-134">È contrassegnata con un'icona distinta e funge da intestazione delle righe consegna.</span><span class="sxs-lookup"><span data-stu-id="d9567-134">It is marked with a distinct icon and acts as a header for the delivery lines.</span></span>  
15. <span data-ttu-id="d9567-135">Selezionare la seconda riga ordine, che è la prima delle due righe di consegna.</span><span class="sxs-lookup"><span data-stu-id="d9567-135">Select the second order line, which is the first of the two delivery lines.</span></span>
    * <span data-ttu-id="d9567-136">Le due nuove righe, denominate righe consegna, costituiscono una programmazione consegna.</span><span class="sxs-lookup"><span data-stu-id="d9567-136">The two new lines, referred to as Delivery lines, make up one delivery schedule.</span></span> <span data-ttu-id="d9567-137">L'ordine verrà elaborato rispetto a queste righe e non alla riga originale.</span><span class="sxs-lookup"><span data-stu-id="d9567-137">The order will be processed against these lines and not the original line.</span></span> <span data-ttu-id="d9567-138">Se i documenti come conferme, giornali di registrazione entrata prodotti o fatture vengono stampati, verranno visualizzate solo le righe consegna.</span><span class="sxs-lookup"><span data-stu-id="d9567-138">If documents such as confirmations, product receipt journals, or invoices are printed, only the delivery lines are shown.</span></span>  

## <a name="change-the-delivery-schedule"></a><span data-ttu-id="d9567-139">Modificare la programmazione consegna</span><span class="sxs-lookup"><span data-stu-id="d9567-139">Change the delivery schedule</span></span>
    * <span data-ttu-id="d9567-140">È possibile modificare la quantità nelle righe consegna.</span><span class="sxs-lookup"><span data-stu-id="d9567-140">You can change the quantity on delivery lines.</span></span> <span data-ttu-id="d9567-141">In questo caso, la riga commerciale viene aggiornata automaticamente in base alla quantità totale delle righe di consegna.</span><span class="sxs-lookup"><span data-stu-id="d9567-141">If you do this, the commercial line is automatically updated to the total quantity in the delivery lines.</span></span>  
1. <span data-ttu-id="d9567-142">Nel campo Quantità della riga della prima consegna cambiare la quantità da 4 a 5.</span><span class="sxs-lookup"><span data-stu-id="d9567-142">In the Quantity field of the first delivery line, change the quantity from 4 to 5.</span></span>
2. <span data-ttu-id="d9567-143">Selezionare la prima riga di ordine (la riga commerciale).</span><span class="sxs-lookup"><span data-stu-id="d9567-143">Select the first order line (the commercial line).</span></span>
    * <span data-ttu-id="d9567-144">La quantità della linea commerciale è stata cambiata in 11.</span><span class="sxs-lookup"><span data-stu-id="d9567-144">The quantity on the commercial line has been changed to 11.</span></span>  

## <a name="process-product-receipt-using-delivery-schedules"></a><span data-ttu-id="d9567-145">Elaborare l'entrata prodotti facendo uso delle programmazioni consegna</span><span class="sxs-lookup"><span data-stu-id="d9567-145">Process product receipt using delivery schedules</span></span>
    * <span data-ttu-id="d9567-146">L'ordine fornitore deve essere confermato prima che l'entrata prodotti possa essere elaborata.</span><span class="sxs-lookup"><span data-stu-id="d9567-146">The purchase order must be confirmed before product receipt can be processed.</span></span> <span data-ttu-id="d9567-147">In questo esempio, l'entrata è registrata direttamente nell'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="d9567-147">In this example, receipt is recorded directly on the purchase order.</span></span> <span data-ttu-id="d9567-148">L'entrata potrebbe anche essere stata registrata quando le merci sono arrivate nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="d9567-148">Receipt could also have been recorded when the goods arrived in the warehouse.</span></span>  
1. <span data-ttu-id="d9567-149">Nel riquadro azioni fare clic su Acquisti.</span><span class="sxs-lookup"><span data-stu-id="d9567-149">On the Action Pane, click Purchase.</span></span>
2. <span data-ttu-id="d9567-150">Fare clic su Conferma.</span><span class="sxs-lookup"><span data-stu-id="d9567-150">Click Confirm.</span></span>
3. <span data-ttu-id="d9567-151">Nel riquadro azioni fare clic su Ricevimento.</span><span class="sxs-lookup"><span data-stu-id="d9567-151">On the Action Pane, click Receive.</span></span>
4. <span data-ttu-id="d9567-152">Fare clic su Entrata prodotti.</span><span class="sxs-lookup"><span data-stu-id="d9567-152">Click Product receipt.</span></span>
5. <span data-ttu-id="d9567-153">Digitare un valore nel campo Entrata prodotti.</span><span class="sxs-lookup"><span data-stu-id="d9567-153">In the Product receipt field, type any value.</span></span>
    * <span data-ttu-id="d9567-154">Questo campo è usato per immettere un riferimento che sarà usato come giustificativo per il giornale di registrazione entrata prodotti.</span><span class="sxs-lookup"><span data-stu-id="d9567-154">This field is used to enter a reference that will be used as voucher for the product receipt journal.</span></span>  
    * <span data-ttu-id="d9567-155">Nel campo Quantità, selezionare ‘Quantità ordinata’.</span><span class="sxs-lookup"><span data-stu-id="d9567-155">In the Quantity field, select ‘Ordered quantity’.</span></span> <span data-ttu-id="d9567-156">Questa opzione significa che l'entrata verrà elaborata per la quantità con cui sono state create le righe ordine.</span><span class="sxs-lookup"><span data-stu-id="d9567-156">This option means that receipt will process for the quantity that the order lines were created with.</span></span>  
    * <span data-ttu-id="d9567-157">Assicurarsi che il campo Stampa entrata prodotti sia impostato su No.</span><span class="sxs-lookup"><span data-stu-id="d9567-157">Make sure that the Print product receipt field is set to No.</span></span> <span data-ttu-id="d9567-158">La stampa non è necessaria in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="d9567-158">Printing isn’t needed in this example.</span></span>  
6. <span data-ttu-id="d9567-159">Espandere la sezione Righe.</span><span class="sxs-lookup"><span data-stu-id="d9567-159">Expand the Lines section.</span></span>
    * <span data-ttu-id="d9567-160">Notare come l'entrata prodotti è creata per le due righe di consegna e non riga ordine originale.</span><span class="sxs-lookup"><span data-stu-id="d9567-160">Notice how the product receipt is created for the two delivery lines and not the original order line.</span></span> <span data-ttu-id="d9567-161">Se l'entrata fosse stata registrata nel magazzino, sarebbe stata registrata anche nelle righe di programmazione consegna.</span><span class="sxs-lookup"><span data-stu-id="d9567-161">If receipt had been recorded in the warehouse, it would also have been recorded on the delivery schedule lines.</span></span>  
7. <span data-ttu-id="d9567-162">Comprimere la sezione Righe.</span><span class="sxs-lookup"><span data-stu-id="d9567-162">Collapse the Lines section.</span></span>
8. <span data-ttu-id="d9567-163">Fare clic su OK per registrare l'entrata.</span><span class="sxs-lookup"><span data-stu-id="d9567-163">Click OK to post the receipt.</span></span>

