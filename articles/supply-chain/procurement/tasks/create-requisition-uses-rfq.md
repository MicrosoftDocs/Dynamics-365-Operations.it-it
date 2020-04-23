---
title: Creare una richiesta che usa una RdO
description: In questo argomento viene descritto come aggiungere le informazioni su prezzo e fornitore ad una richiesta di acquisto da un processo di RdO.
author: mkirknel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqLineRelatedDocuments, EcoResCategorySingleLookup, PurchReqWorkflowDropDialog, WorkflowSubmitDialog, WorkflowStatus, WorkflowWorkItemActionDialog, WorkflowUserListLookup, PurchReqCopyRFQ, SysDataAreaSelectLookup, PurchRFQCaseTable, PurchRFQEditLines, PurchRFQReplyTable, UnitOfMeasureLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 205cba2325e76dae9572301e44e0e89cbcfd106e
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204702"
---
# <a name="create-a-requisition-that-uses-an-rfq"></a><span data-ttu-id="c5c17-103">Creare una richiesta che usa una RdO</span><span class="sxs-lookup"><span data-stu-id="c5c17-103">Create a requisition that uses an RFQ</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c5c17-104">In questo argomento viene descritto come aggiungere le informazioni su prezzo e fornitore ad una richiesta di acquisto da un processo di RdO.</span><span class="sxs-lookup"><span data-stu-id="c5c17-104">This topic explains how to add price and vendor information to a purchase requisition from an RFQ process.</span></span> <span data-ttu-id="c5c17-105">L'esempio indicato in questa guida può essere utilizzato nella società di dati dimostrativi USMF e dovete essere collegati come Amministratore per completare tutti i passaggi.</span><span class="sxs-lookup"><span data-stu-id="c5c17-105">The example shown in this guide can be used in the USMF demo data company, and you must be logged in as an Admin to complete all the steps.</span></span> <span data-ttu-id="c5c17-106">Le attività in questa guida sarebbero svolte tipicamente da professionisti dell'approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="c5c17-106">The tasks in this guide would typically be done by procurement professionals.</span></span>


## <a name="create-a-requisition"></a><span data-ttu-id="c5c17-107">Creare una richiesta</span><span class="sxs-lookup"><span data-stu-id="c5c17-107">Create a requisition</span></span>
1. <span data-ttu-id="c5c17-108">Nel pannello di navigazione, andare a **Moduli > Approvvigionamento > Richieste di acquisto > Richieste di acquisto preparate dall'utente**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-108">In the navigation pane, go to **Modules > Procurement and sourcing > Purchase requisitions > Purchase requisitions prepared by me**.</span></span>
2. <span data-ttu-id="c5c17-109">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-109">Select **New**.</span></span>
3. <span data-ttu-id="c5c17-110">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-110">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="c5c17-111">Nel campo **Data richiesta** immettere una data.</span><span class="sxs-lookup"><span data-stu-id="c5c17-111">In the **Requested date** field, enter a date.</span></span>
5. <span data-ttu-id="c5c17-112">Immettere una data nel campo **Data di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-112">In the **Accounting date** field, enter a date.</span></span>
6. <span data-ttu-id="c5c17-113">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-113">Select **OK**.</span></span>
7. <span data-ttu-id="c5c17-114">Nel campo **Motivo** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c5c17-114">In the **Reason** field, enter or select a value.</span></span>
8. <span data-ttu-id="c5c17-115">Selezionare **Aggiungi riga**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-115">Select **Add line**.</span></span>
9. <span data-ttu-id="c5c17-116">Nel campo **Categoria di approvvigionamento**, selezionare una categoria nella struttura e poi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-116">In the **Procurement category** field, select a category in the tree, and then select **OK**.</span></span>
10. <span data-ttu-id="c5c17-117">Digitare un valore nel campo **Nome prodotto**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-117">In the **Product name** field, type a value.</span></span>
11. <span data-ttu-id="c5c17-118">Nel campo **Quantità** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="c5c17-118">In the **Quantity** field, enter a number.</span></span>
12. <span data-ttu-id="c5c17-119">Nel campo **Unità** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c5c17-119">In the **Unit** field, enter or select a value.</span></span>
13. <span data-ttu-id="c5c17-120">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-120">Select **Save**.</span></span>
14. <span data-ttu-id="c5c17-121">Fare clic su **Flusso di lavoro** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="c5c17-121">Select **Workflow** to open the drop dialog.</span></span>
15. <span data-ttu-id="c5c17-122">Selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-122">Select **Submit**.</span></span>
16. <span data-ttu-id="c5c17-123">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c5c17-123">Close the page.</span></span>
17. <span data-ttu-id="c5c17-124">Selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-124">Select **Submit**.</span></span>

## <a name="reassign-a-workflow-task"></a><span data-ttu-id="c5c17-125">Riassegnare un'attività di flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="c5c17-125">Reassign a workflow task</span></span>
<span data-ttu-id="c5c17-126">L'attività seguente è creare una RdO per ottenere le offerte dai fornitori per il prodotto.</span><span class="sxs-lookup"><span data-stu-id="c5c17-126">The next task is to create an RFQ to get bids from vendors for the product.</span></span> <span data-ttu-id="c5c17-127">Nei dati dimostrativi USMF, il flusso di lavoro di richiesta è impostato con una regola in modo che se un fornitore non è selezionato, o il prezzo unitario è 0 per una riga, un'attività viene assegnata ad un lavoratore specifico per creare una RdO.</span><span class="sxs-lookup"><span data-stu-id="c5c17-127">In USMF demo data, the requisition workflow is set up with a rule so that if a vendor is not selected, or the unit price is 0 for a line, a task is assigned to a specific worker to create an RFQ.</span></span> <span data-ttu-id="c5c17-128">Per continuare con questa guida, dovete riassegnare quell'attività ad un altro utente (voi stessi).</span><span class="sxs-lookup"><span data-stu-id="c5c17-128">To continue with this guide, you need to re-assign that task to another user (yourself).</span></span> <span data-ttu-id="c5c17-129">Potete fare questo solo se siete collegati come Amministratore.</span><span class="sxs-lookup"><span data-stu-id="c5c17-129">You can only do this if you are logged in as an Admin.</span></span>  

1. <span data-ttu-id="c5c17-130">Fare clic su **Flusso di lavoro** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="c5c17-130">Select **Workflow** to open the drop dialog.</span></span>
2. <span data-ttu-id="c5c17-131">Selezionare **Visualizza storico**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-131">Select **View history**.</span></span>
3. <span data-ttu-id="c5c17-132">Aggiorna la pagina.</span><span class="sxs-lookup"><span data-stu-id="c5c17-132">Refresh the page.</span></span>
4. <span data-ttu-id="c5c17-133">Espandere la sezione **Dettagli tracciabilità**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-133">Expand the **Tracking details** section.</span></span>
5. <span data-ttu-id="c5c17-134">Nella struttura, selezionare la riga che inizia con "Flusso di lavoro voci attivato il".</span><span class="sxs-lookup"><span data-stu-id="c5c17-134">In the tree, select the line that starts with "Line workflow activated on".</span></span>
6. <span data-ttu-id="c5c17-135">Selezionare **Visualizza dettagli flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-135">Select **View workflow details**.</span></span>
7. <span data-ttu-id="c5c17-136">Espandere la sezione **Elementi di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-136">Expand the **Work items** section.</span></span>
8. <span data-ttu-id="c5c17-137">Selezionare **Riassegna**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-137">Select **Reassign**.</span></span>
9. <span data-ttu-id="c5c17-138">Nel campo **Utente**, selezionare **Amministratore**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-138">In the **User** field, select **Admin**.</span></span>
10. <span data-ttu-id="c5c17-139">Selezionare **Riassegna**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-139">Select **Reassign**.</span></span>
11. <span data-ttu-id="c5c17-140">Chiudere le due pagine.</span><span class="sxs-lookup"><span data-stu-id="c5c17-140">Close the two pages.</span></span>

## <a name="create-an-rfq"></a><span data-ttu-id="c5c17-141">Creare una RdO</span><span class="sxs-lookup"><span data-stu-id="c5c17-141">Create an RFQ</span></span>

1. <span data-ttu-id="c5c17-142">Aggiorna la pagina.</span><span class="sxs-lookup"><span data-stu-id="c5c17-142">Refresh the page.</span></span>
2. <span data-ttu-id="c5c17-143">Selezionare **Richiesta di offerta**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-143">Select **Request for quotation**.</span></span>
3. <span data-ttu-id="c5c17-144">Nel campo **Persona giuridica acquirente**, selezionare **USMF**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-144">In the **Buying legal entity** field, select **USMF**.</span></span> <span data-ttu-id="c5c17-145">È necessario selezionare la stessa persona giuridica presente sulla riga di richiesta.</span><span class="sxs-lookup"><span data-stu-id="c5c17-145">You must select the same legal entity that's on the requisition line.</span></span>  
4. <span data-ttu-id="c5c17-146">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="c5c17-146">In the list, mark the selected row.</span></span> <span data-ttu-id="c5c17-147">Se aveste più righe nella richiesta di acquisto, selezionare tutte le righe che volete aggiungere al RdO.</span><span class="sxs-lookup"><span data-stu-id="c5c17-147">If you had multiple lines on your purchase requisition, select all the lines that you want to add to the RFQ.</span></span>  
5. <span data-ttu-id="c5c17-148">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-148">Select **OK**.</span></span>
6. <span data-ttu-id="c5c17-149">Aggiorna la pagina.</span><span class="sxs-lookup"><span data-stu-id="c5c17-149">Refresh the page.</span></span>
7. <span data-ttu-id="c5c17-150">Assicurarsi che la Scheda dettaglio sia aperta, quindi espandere la sezione **Documenti correlati**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-150">Ensure that the FactBox is open, then expand the **Related documents** section.</span></span>
8. <span data-ttu-id="c5c17-151">Selezionare il collegamento nel campo **Richiesta di offerta** per aprire l'RdO appena creata.</span><span class="sxs-lookup"><span data-stu-id="c5c17-151">Select the link in the **Request for quotation** field to open the RFQ that was just created.</span></span>
9. <span data-ttu-id="c5c17-152">Selezionare **Intestazione**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-152">Select **Header**.</span></span>
10. <span data-ttu-id="c5c17-153">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-153">Select **Add**.</span></span>
11. <span data-ttu-id="c5c17-154">Nel campo **Conto fornitore**, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c5c17-154">In the **Vendor account** field, enter or select a value.</span></span>
12. <span data-ttu-id="c5c17-155">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-155">Select **Add**.</span></span>
13. <span data-ttu-id="c5c17-156">Nel campo **Conto fornitore**, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c5c17-156">In the **Vendor account** field, enter or select a value.</span></span>
14. <span data-ttu-id="c5c17-157">Selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-157">Select **Send**.</span></span>
15. <span data-ttu-id="c5c17-158">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-158">Select **OK**.</span></span>
16. <span data-ttu-id="c5c17-159">Selezionare **Inserisci risposta**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-159">Select **Enter reply**.</span></span>
17. <span data-ttu-id="c5c17-160">Nel Riquadro azioni fare clic su **Rispondi**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-160">On the Action Pane, select **Reply**.</span></span>
18. <span data-ttu-id="c5c17-161">Selezionare **Copia dati nella risposta**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-161">Select **Copy data to reply**.</span></span> <span data-ttu-id="c5c17-162">Ciò copia i dati, quali la quantità e le date, dalla RdO alla risposta.</span><span class="sxs-lookup"><span data-stu-id="c5c17-162">This copies data, such as the quantity and dates, from the RFQ to the reply.</span></span>  
19. <span data-ttu-id="c5c17-163">Immettere un numero nel campo **Prezzo unitario**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-163">In the **Unit price** field, enter a number.</span></span> <span data-ttu-id="c5c17-164">Questo è il prezzo ricevuto dal fornitore.</span><span class="sxs-lookup"><span data-stu-id="c5c17-164">This is the price that you've received from the vendor.</span></span> <span data-ttu-id="c5c17-165">Potreste anche volere immettere ulteriori informazioni dal fornitore.</span><span class="sxs-lookup"><span data-stu-id="c5c17-165">You might also want to enter additional information from the vendor.</span></span>  
20. <span data-ttu-id="c5c17-166">Selezionare **Accetta**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-166">Select **Accept**.</span></span>
21. <span data-ttu-id="c5c17-167">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-167">Select **OK**.</span></span>

## <a name="verify-that-vendor-and-price-have-been-transferred-to-the-requisition"></a><span data-ttu-id="c5c17-168">Verificare che il prezzo ed il fornitore siano stati trasferiti nella richiesta</span><span class="sxs-lookup"><span data-stu-id="c5c17-168">Verify that vendor and price have been transferred to the requisition</span></span>
1. <span data-ttu-id="c5c17-169">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c5c17-169">Close the page.</span></span>
2. <span data-ttu-id="c5c17-170">Selezionare **Righe**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-170">Select **Lines**.</span></span>
3. <span data-ttu-id="c5c17-171">Selezionare **Informazioni correlate**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-171">Select **Related information**.</span></span>
4. <span data-ttu-id="c5c17-172">Seelzionare **Richiesta di acquisto**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-172">Select **Purchase requisition**.</span></span>
5. <span data-ttu-id="c5c17-173">Selezionare la riga che è stata trasferita alla RdO.</span><span class="sxs-lookup"><span data-stu-id="c5c17-173">Select the line that was transferred to the RFQ.</span></span> <span data-ttu-id="c5c17-174">Verificare che il prezzo ed il fornitore siano stati copiati nella richiesta.</span><span class="sxs-lookup"><span data-stu-id="c5c17-174">Verify that the price and vendor have been copied to the requisition.</span></span>  
6. <span data-ttu-id="c5c17-175">Fare clic su **Flusso di lavoro** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="c5c17-175">Select **Workflow** to open the drop dialog.</span></span>
7. <span data-ttu-id="c5c17-176">Seleziona Completa.</span><span class="sxs-lookup"><span data-stu-id="c5c17-176">Select Complete.</span></span>
8. <span data-ttu-id="c5c17-177">Selezionare la pagina.</span><span class="sxs-lookup"><span data-stu-id="c5c17-177">Select the page.</span></span>
9. <span data-ttu-id="c5c17-178">Seleziona Completa.</span><span class="sxs-lookup"><span data-stu-id="c5c17-178">Select Complete.</span></span>

