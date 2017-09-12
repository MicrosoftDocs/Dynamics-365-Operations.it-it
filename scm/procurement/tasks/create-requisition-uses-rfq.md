--- 
title: Creare una richiesta che usa una RdO
description: Questa guida mostra come aggiungere le informazioni su prezzo e fornitore ad una richiesta di acquisto da un processo di RdO.
author: mkirknel
manager: AnnBe
ms.date: 08/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: d97ccd15031b2f7398486eee4a716ecef5e9dafd
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-requisition-that-uses-an-rfq"></a><span data-ttu-id="72952-103">Creare una richiesta che usa una RdO</span><span class="sxs-lookup"><span data-stu-id="72952-103">Create a requisition that uses an RFQ</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="72952-104">Questa guida mostra come aggiungere le informazioni su prezzo e fornitore ad una richiesta di acquisto da un processo di RdO.</span><span class="sxs-lookup"><span data-stu-id="72952-104">This guide shows how to add price and vendor information to a purchase requisition from an RFQ process.</span></span> <span data-ttu-id="72952-105">L'esempio indicato in questa guida può essere utilizzato nella società di dati dimostrativi USMF e dovete essere collegati come Amministratore per completare tutti i passaggi.</span><span class="sxs-lookup"><span data-stu-id="72952-105">The example shown in this guide can be used in the USMF demo data company, and you must be logged in as an Admin to complete all the steps.</span></span> <span data-ttu-id="72952-106">Le attività in questa guida sarebbero svolte tipicamente da professionisti dell'approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="72952-106">The tasks in this guide would typically be done by procurement professionals.</span></span>


## <a name="create-a-requisition"></a><span data-ttu-id="72952-107">Creare una richiesta</span><span class="sxs-lookup"><span data-stu-id="72952-107">Create a requisition</span></span>
1. <span data-ttu-id="72952-108">Andare ad Approvvigionamento > Richieste di acquisto > Richieste di acquisto preparate dall'utente.</span><span class="sxs-lookup"><span data-stu-id="72952-108">Go to Procurement and sourcing > Purchase requisitions > Purchase requisitions prepared by me.</span></span>
2. <span data-ttu-id="72952-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="72952-109">Click New.</span></span>
3. <span data-ttu-id="72952-110">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="72952-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="72952-111">Nel campo Data richiesta immettere una data.</span><span class="sxs-lookup"><span data-stu-id="72952-111">In the Requested date field, enter a date.</span></span>
5. <span data-ttu-id="72952-112">Immettere una data nel campo Data di registrazione.</span><span class="sxs-lookup"><span data-stu-id="72952-112">In the Accounting date field, enter a date.</span></span>
6. <span data-ttu-id="72952-113">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="72952-113">Click OK.</span></span>
7. <span data-ttu-id="72952-114">Nel campo Motivo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="72952-114">In the Reason field, enter or select a value.</span></span>
8. <span data-ttu-id="72952-115">Fare clic su Aggiungi riga.</span><span class="sxs-lookup"><span data-stu-id="72952-115">Click Add line.</span></span>
9. <span data-ttu-id="72952-116">Nel campo Categoria di approvvigionamento, selezionare una categoria nella struttura e poi fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="72952-116">In the Procurement category field, select a category in the tree, and then click OK.</span></span>
10. <span data-ttu-id="72952-117">Digitare un valore nel campo Nome prodotto.</span><span class="sxs-lookup"><span data-stu-id="72952-117">In the Product name field, type a value.</span></span>
11. <span data-ttu-id="72952-118">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="72952-118">In the Quantity field, enter a number.</span></span>
12. <span data-ttu-id="72952-119">Nel campo Unità immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="72952-119">In the Unit field, enter or select a value.</span></span>
13. <span data-ttu-id="72952-120">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="72952-120">Click Save.</span></span>
14. <span data-ttu-id="72952-121">Fare clic su Flusso di lavoro per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="72952-121">Click Workflow to open the drop dialog.</span></span>
15. <span data-ttu-id="72952-122">Fare clic su Invia.</span><span class="sxs-lookup"><span data-stu-id="72952-122">Click Submit.</span></span>
16. <span data-ttu-id="72952-123">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="72952-123">Close the page.</span></span>
17. <span data-ttu-id="72952-124">Fare clic su Invia.</span><span class="sxs-lookup"><span data-stu-id="72952-124">Click Submit.</span></span>

## <a name="reassign-a-workflow-task"></a><span data-ttu-id="72952-125">Riassegnare un'attività di flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="72952-125">Reassign a workflow task</span></span>
    * <span data-ttu-id="72952-126">L'attività seguente è creare una RdO per ottenere le offerte dai fornitori per il prodotto.</span><span class="sxs-lookup"><span data-stu-id="72952-126">The next task is to create an RFQ to get bids from vendors for the product.</span></span> <span data-ttu-id="72952-127">Nei dati dimostrativi USMF, il flusso di lavoro di richiesta è impostato con una regola in modo che se un fornitore non è selezionato, o il prezzo unitario è 0 per una riga, un'attività viene assegnata ad un lavoratore specifico per creare una RdO.</span><span class="sxs-lookup"><span data-stu-id="72952-127">In USMF demo data, the requisition workflow is set up with a rule so that if a vendor is not selected, or the unit price is 0 for a line, a task is assigned to a specific worker to create an RFQ.</span></span> <span data-ttu-id="72952-128">Per continuare con questa guida, dovete riassegnare quell'attività ad un altro utente (voi stessi).</span><span class="sxs-lookup"><span data-stu-id="72952-128">To continue with this guide, you need to re-assign that task to another user (yourself).</span></span> <span data-ttu-id="72952-129">Potete fare questo solo se siete collegati come Amministratore.</span><span class="sxs-lookup"><span data-stu-id="72952-129">You can only do this if you are logged in as an Admin.</span></span>  
1. <span data-ttu-id="72952-130">Fare clic su Flusso di lavoro per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="72952-130">Click Workflow to open the drop dialog.</span></span>
2. <span data-ttu-id="72952-131">Fare clic su Visualizza storico,</span><span class="sxs-lookup"><span data-stu-id="72952-131">Click View history.</span></span>
3. <span data-ttu-id="72952-132">Aggiorna la pagina.</span><span class="sxs-lookup"><span data-stu-id="72952-132">Refresh the page.</span></span>
4. <span data-ttu-id="72952-133">Espandere la sezione Dettagli tracciabilità.</span><span class="sxs-lookup"><span data-stu-id="72952-133">Expand the Tracking details section.</span></span>
5. <span data-ttu-id="72952-134">Nella struttura, selezionare la riga che inizia con 'Flusso di lavoro voci attivato il'.</span><span class="sxs-lookup"><span data-stu-id="72952-134">In the tree, select 'the line that starts with “Line workflow activated on”'.</span></span>
6. <span data-ttu-id="72952-135">Fare clic su Visualizza dettagli flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="72952-135">Click View workflow details.</span></span>
7. <span data-ttu-id="72952-136">Espandere la sezione Elementi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="72952-136">Expand the Work items section.</span></span>
8. <span data-ttu-id="72952-137">Fare clic su Riassegna.</span><span class="sxs-lookup"><span data-stu-id="72952-137">Click Reassign.</span></span>
9. <span data-ttu-id="72952-138">Nel campo Utente, selezionare Amministratore.</span><span class="sxs-lookup"><span data-stu-id="72952-138">In the User field, select Admin.</span></span>
10. <span data-ttu-id="72952-139">Fare clic su Riassegna.</span><span class="sxs-lookup"><span data-stu-id="72952-139">Click Reassign.</span></span>
11. <span data-ttu-id="72952-140">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="72952-140">Close the page.</span></span>
12. <span data-ttu-id="72952-141">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="72952-141">Close the page.</span></span>

## <a name="create-an-rfq"></a><span data-ttu-id="72952-142">Creare una RdO</span><span class="sxs-lookup"><span data-stu-id="72952-142">Create an RFQ</span></span>
1. <span data-ttu-id="72952-143">Aggiorna la pagina.</span><span class="sxs-lookup"><span data-stu-id="72952-143">Refresh the page.</span></span>
2. <span data-ttu-id="72952-144">Fare clic su Richiesta di offerta.</span><span class="sxs-lookup"><span data-stu-id="72952-144">Click Request for quotation.</span></span>
3. <span data-ttu-id="72952-145">Nel campo Persona giuridica acquirente, selezionare USMF.</span><span class="sxs-lookup"><span data-stu-id="72952-145">In the Buying legal entity field, select USMF.</span></span>
    * <span data-ttu-id="72952-146">Dovete selezionare la stessa persona giuridica che è sulla riga di richiesta.</span><span class="sxs-lookup"><span data-stu-id="72952-146">You must select the same legal entity that’s on the requisition line.</span></span>  
4. <span data-ttu-id="72952-147">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="72952-147">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="72952-148">Se aveste più righe nella richiesta di acquisto, selezionare tutte le righe che volete aggiungere al RdO.</span><span class="sxs-lookup"><span data-stu-id="72952-148">If you had multiple lines on your purchase requisition, select all the lines that you want to add to the RFQ.</span></span>  
5. <span data-ttu-id="72952-149">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="72952-149">Click OK.</span></span>
6. <span data-ttu-id="72952-150">Aggiorna la pagina.</span><span class="sxs-lookup"><span data-stu-id="72952-150">Refresh the page.</span></span>
7. <span data-ttu-id="72952-151">Aprire il Dettaglio informazioni, quindi espandere la sezione Documenti correlati.</span><span class="sxs-lookup"><span data-stu-id="72952-151">Open the FactBox and then expand the Related documents section.</span></span>
    * <span data-ttu-id="72952-152">È possibile che il Dettaglio informazioni sia già aperto.</span><span class="sxs-lookup"><span data-stu-id="72952-152">You may already have the FactBox open.</span></span> <span data-ttu-id="72952-153">Cercare l'icona con una freccia, a destra degli interruttori Righe/Intestazione.</span><span class="sxs-lookup"><span data-stu-id="72952-153">Look for the icon with an arrow on it, to the right of the Lines/Header toggle buttons.</span></span> <span data-ttu-id="72952-154">Se la freccia sta indicando la destra, il Dettaglio informazioni è già aperto.</span><span class="sxs-lookup"><span data-stu-id="72952-154">If the arrow is pointing to the right, the FactBox is already open.</span></span> <span data-ttu-id="72952-155">Se la freccia indica a sinistra, fare clic per aprire il Dettaglio informazioni.</span><span class="sxs-lookup"><span data-stu-id="72952-155">If the arrow points to the left, click it to open the FactBox.</span></span>  
8. <span data-ttu-id="72952-156">Fare clic sul collegamento nel campo Richiesta di offerta per aprire l'RdO appena creata.</span><span class="sxs-lookup"><span data-stu-id="72952-156">Click the link in the Request for quotation field to open the RFQ that was just created.</span></span>
9. <span data-ttu-id="72952-157">Fare clic su Intestazione.</span><span class="sxs-lookup"><span data-stu-id="72952-157">Click Header.</span></span>
10. <span data-ttu-id="72952-158">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="72952-158">Click Add.</span></span>
11. <span data-ttu-id="72952-159">Nel campo Conto fornitore, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="72952-159">In the Vendor account field, enter or select a value.</span></span>
12. <span data-ttu-id="72952-160">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="72952-160">Click Add.</span></span>
13. <span data-ttu-id="72952-161">Nel campo Conto fornitore, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="72952-161">In the Vendor account field, enter or select a value.</span></span>
14. <span data-ttu-id="72952-162">Fare clic su Invia.</span><span class="sxs-lookup"><span data-stu-id="72952-162">Click Send.</span></span>
15. <span data-ttu-id="72952-163">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="72952-163">Click OK.</span></span>
16. <span data-ttu-id="72952-164">Fare clic su Inserisci risposta.</span><span class="sxs-lookup"><span data-stu-id="72952-164">Click Enter reply.</span></span>
17. <span data-ttu-id="72952-165">Nel Riquadro azioni fare clic su Rispondi.</span><span class="sxs-lookup"><span data-stu-id="72952-165">On the Action Pane, click Reply.</span></span>
18. <span data-ttu-id="72952-166">Fare clic su Copia dati per rispondere.</span><span class="sxs-lookup"><span data-stu-id="72952-166">Click Copy data to reply.</span></span>
    * <span data-ttu-id="72952-167">Ciò copia i dati, quali la quantità e le date, dalla RdO alla risposta.</span><span class="sxs-lookup"><span data-stu-id="72952-167">This copies data, such as the quantity and dates, from the RFQ to the reply .</span></span>  
19. <span data-ttu-id="72952-168">Nel campo Prezzo unitario immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="72952-168">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="72952-169">Questo è il prezzo che avete ricevuto dal fornitore.</span><span class="sxs-lookup"><span data-stu-id="72952-169">This is the price that you’ve received from the vendor.</span></span> <span data-ttu-id="72952-170">Potreste anche volere immettere ulteriori informazioni dal fornitore.</span><span class="sxs-lookup"><span data-stu-id="72952-170">You might also want to enter additional information from the vendor.</span></span>  
20. <span data-ttu-id="72952-171">Fare clic su Accetta.</span><span class="sxs-lookup"><span data-stu-id="72952-171">Click Accept.</span></span>
21. <span data-ttu-id="72952-172">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="72952-172">Click OK.</span></span>

## <a name="verify-that-vendor-and-price-have-been-transferred-to-the-requisition"></a><span data-ttu-id="72952-173">Verificare che il prezzo ed il fornitore siano stati trasferiti nella richiesta</span><span class="sxs-lookup"><span data-stu-id="72952-173">Verify that vendor and price have been transferred to the requisition</span></span>
1. <span data-ttu-id="72952-174">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="72952-174">Close the page.</span></span>
2. <span data-ttu-id="72952-175">Fare clic su Righe.</span><span class="sxs-lookup"><span data-stu-id="72952-175">Click Lines.</span></span>
3. <span data-ttu-id="72952-176">Fare clic su Informazioni correlate.</span><span class="sxs-lookup"><span data-stu-id="72952-176">Click Related information.</span></span>
4. <span data-ttu-id="72952-177">Fare clic su Richiesta di acquisto.</span><span class="sxs-lookup"><span data-stu-id="72952-177">Click Purchase requisition.</span></span>
5. <span data-ttu-id="72952-178">Selezionare la riga che è stata trasferita alla RdO.</span><span class="sxs-lookup"><span data-stu-id="72952-178">Select the line that was transferred to the RFQ.</span></span>
    * <span data-ttu-id="72952-179">Verificare che il prezzo ed il fornitore siano stati copiati nella richiesta.</span><span class="sxs-lookup"><span data-stu-id="72952-179">Verify that the price and vendor have been copied to the requisition.</span></span>  
6. <span data-ttu-id="72952-180">Fare clic su Flusso di lavoro per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="72952-180">Click Workflow to open the drop dialog.</span></span>
7. <span data-ttu-id="72952-181">Fare clic su Completa.</span><span class="sxs-lookup"><span data-stu-id="72952-181">Click Complete.</span></span>
8. <span data-ttu-id="72952-182">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="72952-182">Close the page.</span></span>
9. <span data-ttu-id="72952-183">Fare clic su Completa.</span><span class="sxs-lookup"><span data-stu-id="72952-183">Click Complete.</span></span>

