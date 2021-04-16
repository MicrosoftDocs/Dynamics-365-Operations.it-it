---
title: Esportare lettera di credito
description: In questa procedura vengono descritti i passaggi per esportare una lettera di credito.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, DefaultDashboard, SalesTableListPage, SalesCreateOrder, SalesTable, BankLCExport, SalesEditLines,  LedgerJournalTable, LedgerJournalTransCustPaym, CustOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 260ef2d05e1f21708817346af2db2841aa6acdd9
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834790"
---
# <a name="export-letter-of-credit"></a><span data-ttu-id="2573b-103">Esportare lettera di credito</span><span class="sxs-lookup"><span data-stu-id="2573b-103">Export letter of credit</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2573b-104">In questa procedura vengono descritti i passaggi per esportare una lettera di credito.</span><span class="sxs-lookup"><span data-stu-id="2573b-104">This procedure walks through the process of the Export letter of credit.</span></span>

<span data-ttu-id="2573b-105">Una lettere di credito è un contratto emesso da una banca, nel quale la banca acconsente a garantire un pagamento per conto dell'acquirente, qualora vengano osservati i termini del contratto tra l'acquirente e il venditore.</span><span class="sxs-lookup"><span data-stu-id="2573b-105">A letter of credit is an agreement that is issued by a bank, in which the bank agrees to ensure payment on behalf of the buyer, if the terms of the agreement between the buyer and seller are met.</span></span>



<span data-ttu-id="2573b-106">Eseguire la procedura 'Impostare le linee di credito bancarie e i profili registrazione' e la procedura 'Creare un contratto per linea di credito bancaria per la lettera di credito' prima di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="2573b-106">Run the 'Set up bank facilities and posting profiles' procedure and the 'Letter of Credit_Create a bank facility agreement' procedure prior to this procedure.</span></span> <span data-ttu-id="2573b-107">La società di dati dimostrativi USMF deve essere selezionata per eseguire questa procedura correttamente.</span><span class="sxs-lookup"><span data-stu-id="2573b-107">The USMF demo company must be selected in order to run this procedure successfully.</span></span>




## <a name="create-sales-order-for-export-letter-of-credit"></a><span data-ttu-id="2573b-108">Creare un ordine cliente per lettera di credito di esportazione</span><span class="sxs-lookup"><span data-stu-id="2573b-108">Create Sales Order for Export letter of credit</span></span>
1. <span data-ttu-id="2573b-109">Andare a Contabilità clienti > Ordini > Tutti gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="2573b-109">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="2573b-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="2573b-110">Click New.</span></span>
3. <span data-ttu-id="2573b-111">Nel campo Conto cliente fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="2573b-111">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="2573b-112">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="2573b-112">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="2573b-113">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2573b-113">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="2573b-114">Espandere o comprimere la sezione Generale.</span><span class="sxs-lookup"><span data-stu-id="2573b-114">Expand or collapse the General section.</span></span>
7. <span data-ttu-id="2573b-115">Nel campo Sito fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="2573b-115">In the Site field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="2573b-116">Selezionare il sito in cui è stoccato l'articolo da emettere.</span><span class="sxs-lookup"><span data-stu-id="2573b-116">Select the Site where the item to be issued is stocked.</span></span>  
8. <span data-ttu-id="2573b-117">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2573b-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="2573b-118">Nel campo Magazzino fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="2573b-118">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="2573b-119">Selezionare il magazzino in cui è stoccato l'articolo da emettere.</span><span class="sxs-lookup"><span data-stu-id="2573b-119">Select the Warehouse where item to be issued is stocked.</span></span>  
10. <span data-ttu-id="2573b-120">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2573b-120">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="2573b-121">Nota: il campo Tipo di documento bancario deve essere selezionato con il valore Lettera di credito.</span><span class="sxs-lookup"><span data-stu-id="2573b-121">Note: The Bank document type field should be selected with the value 'Letter of credit'.</span></span>  
11. <span data-ttu-id="2573b-122">Selezionare 'Lettera di credito' nel campo Tipo di documento bancario.</span><span class="sxs-lookup"><span data-stu-id="2573b-122">In the Bank document type field, select 'Letter of credit'.</span></span>
12. <span data-ttu-id="2573b-123">Espandere o comprimere la sezione Consegna.</span><span class="sxs-lookup"><span data-stu-id="2573b-123">Expand or collapse the Delivery section.</span></span>
    * <span data-ttu-id="2573b-124">Selezionare Controllo data di consegna = Nessuno.</span><span class="sxs-lookup"><span data-stu-id="2573b-124">Select Delivery date control = None.</span></span>  
13. <span data-ttu-id="2573b-125">Nel campo Data di ricevimento richiesta immettere una data.</span><span class="sxs-lookup"><span data-stu-id="2573b-125">In the Requested receipt date field, enter a date.</span></span>
14. <span data-ttu-id="2573b-126">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2573b-126">Click OK.</span></span>
15. <span data-ttu-id="2573b-127">Nel campo Numero articolo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="2573b-127">In the Item number field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="2573b-128">Selezionare l'articolo richiesto da emettere/vendere.</span><span class="sxs-lookup"><span data-stu-id="2573b-128">Select the required item to be Issued/Sold.</span></span>  
16. <span data-ttu-id="2573b-129">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="2573b-129">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="2573b-130">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2573b-130">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="2573b-131">Immettere un numero nel campo Prezzo unitario.</span><span class="sxs-lookup"><span data-stu-id="2573b-131">In the Unit price field, enter a number.</span></span>
19. <span data-ttu-id="2573b-132">Espandere o comprimere la sezione Dettagli riga.</span><span class="sxs-lookup"><span data-stu-id="2573b-132">Expand or collapse the Line details section.</span></span>
20. <span data-ttu-id="2573b-133">Fare clic sulla scheda Consegna.</span><span class="sxs-lookup"><span data-stu-id="2573b-133">Click the Delivery tab.</span></span>
21. <span data-ttu-id="2573b-134">Nel campo Data di spedizione richiesta immettere una data.</span><span class="sxs-lookup"><span data-stu-id="2573b-134">In the Requested ship date field, enter a date.</span></span>
22. <span data-ttu-id="2573b-135">Nel campo Data di spedizione confermata immettere una data.</span><span class="sxs-lookup"><span data-stu-id="2573b-135">In the Confirmed ship date field, enter a date.</span></span>
23. <span data-ttu-id="2573b-136">Nel riquadro azioni, fare clic su Gestisci.</span><span class="sxs-lookup"><span data-stu-id="2573b-136">On the Action Pane, click Manage.</span></span>
24. <span data-ttu-id="2573b-137">Fare clic su Lettera di credito.</span><span class="sxs-lookup"><span data-stu-id="2573b-137">Click Letter of credit.</span></span>
25. <span data-ttu-id="2573b-138">Digitare un valore nel campo Numero documento bancario.</span><span class="sxs-lookup"><span data-stu-id="2573b-138">In the Bank document number field, type a value.</span></span>
26. <span data-ttu-id="2573b-139">Nel campo Data di scadenza immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="2573b-139">In the Expiration date field, enter a date and time.</span></span>
27. <span data-ttu-id="2573b-140">Espandere o comprimere la sezione Dettagli banca.</span><span class="sxs-lookup"><span data-stu-id="2573b-140">Expand or collapse the Bank details section.</span></span>
28. <span data-ttu-id="2573b-141">Nel campo Banca emittente fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="2573b-141">In the Issuing bank field, click the drop-down button to open the lookup.</span></span>
29. <span data-ttu-id="2573b-142">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2573b-142">In the list, click the link in the selected row.</span></span>
30. <span data-ttu-id="2573b-143">Nel campo Banca avvisante fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="2573b-143">In the Advising bank field, click the drop-down button to open the lookup.</span></span>
31. <span data-ttu-id="2573b-144">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="2573b-144">In the list, find and select the desired record.</span></span>
32. <span data-ttu-id="2573b-145">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2573b-145">In the list, click the link in the selected row.</span></span>
33. <span data-ttu-id="2573b-146">Fare clic su Recupera spedizioni ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="2573b-146">Click Fetch sales order shipments.</span></span>
34. <span data-ttu-id="2573b-147">Fare clic su Emetti documento bancario.</span><span class="sxs-lookup"><span data-stu-id="2573b-147">Click Issue bank document.</span></span>
35. <span data-ttu-id="2573b-148">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2573b-148">Close the page.</span></span>

## <a name="post-packing-slip"></a><span data-ttu-id="2573b-149">Registrare il documento di trasporto</span><span class="sxs-lookup"><span data-stu-id="2573b-149">Post Packing slip</span></span>
1. <span data-ttu-id="2573b-150">Nel riquadro azioni fare clic su Preleva e imballa.</span><span class="sxs-lookup"><span data-stu-id="2573b-150">On the Action Pane, click Pick and pack.</span></span>
2. <span data-ttu-id="2573b-151">Fare clic su Registra documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="2573b-151">Click Post packing slip.</span></span>
3. <span data-ttu-id="2573b-152">Espandere o comprimere la sezione Parametri.</span><span class="sxs-lookup"><span data-stu-id="2573b-152">Expand or collapse the Parameters section.</span></span>
4. <span data-ttu-id="2573b-153">Nel campo Quantità selezionare "Tutto".</span><span class="sxs-lookup"><span data-stu-id="2573b-153">In the Quantity field, select 'All'.</span></span>
5. <span data-ttu-id="2573b-154">Espandere o comprimere la sezione Impostazione.</span><span class="sxs-lookup"><span data-stu-id="2573b-154">Expand or collapse the Setup section.</span></span>
6. <span data-ttu-id="2573b-155">Immettere una data nel campo Data documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="2573b-155">In the Packing slip date field, enter a date.</span></span>
7. <span data-ttu-id="2573b-156">Selezionare il numero spedizione.</span><span class="sxs-lookup"><span data-stu-id="2573b-156">Select the Shipment number.</span></span>
8. <span data-ttu-id="2573b-157">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2573b-157">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="2573b-158">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2573b-158">Click OK.</span></span>
10. <span data-ttu-id="2573b-159">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2573b-159">Click OK.</span></span>

## <a name="post-sales-invoice"></a><span data-ttu-id="2573b-160">Registrare la fattura di vendita</span><span class="sxs-lookup"><span data-stu-id="2573b-160">Post sales invoice</span></span>
1. <span data-ttu-id="2573b-161">Nel riquadro azioni fare clic su Fattura.</span><span class="sxs-lookup"><span data-stu-id="2573b-161">On the Action Pane, click Invoice.</span></span>
2. <span data-ttu-id="2573b-162">Fare clic su Fattura.</span><span class="sxs-lookup"><span data-stu-id="2573b-162">Click Invoice.</span></span>
3. <span data-ttu-id="2573b-163">Espandere o comprimere la sezione Panoramica.</span><span class="sxs-lookup"><span data-stu-id="2573b-163">Expand or collapse the Overview section.</span></span>
4. <span data-ttu-id="2573b-164">Selezionare il numero spedizione.</span><span class="sxs-lookup"><span data-stu-id="2573b-164">Select the Shipment number.</span></span>
5. <span data-ttu-id="2573b-165">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2573b-165">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="2573b-166">Espandere o comprimere la sezione Impostazione.</span><span class="sxs-lookup"><span data-stu-id="2573b-166">Expand or collapse the Setup section.</span></span>
7. <span data-ttu-id="2573b-167">Immettere una data nel campo Data fattura.</span><span class="sxs-lookup"><span data-stu-id="2573b-167">In the Invoice date field, enter a date.</span></span>
8. <span data-ttu-id="2573b-168">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2573b-168">Click OK.</span></span>
9. <span data-ttu-id="2573b-169">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2573b-169">Click OK.</span></span>

## <a name="shipment-document-submitted-status"></a><span data-ttu-id="2573b-170">Stato del documento di spedizione inviato</span><span class="sxs-lookup"><span data-stu-id="2573b-170">Shipment document submitted status</span></span>
1. <span data-ttu-id="2573b-171">Nel riquadro azioni, fare clic su Gestisci.</span><span class="sxs-lookup"><span data-stu-id="2573b-171">On the Action Pane, click Manage.</span></span>
2. <span data-ttu-id="2573b-172">Fare clic su Lettera di credito.</span><span class="sxs-lookup"><span data-stu-id="2573b-172">Click Letter of credit.</span></span>
3. <span data-ttu-id="2573b-173">Espandere o comprimere la sezione Righe.</span><span class="sxs-lookup"><span data-stu-id="2573b-173">Expand or collapse the Lines section.</span></span>
    * <span data-ttu-id="2573b-174">Nota: il campo inviato 'Documento inviato' deve essere impostato 'Sì'.</span><span class="sxs-lookup"><span data-stu-id="2573b-174">Note: The 'Document submitted' field should be set to 'Yes'.</span></span>  

## <a name="verify-export-letter-of-credit"></a><span data-ttu-id="2573b-175">Verificare la lettera di credito di esportazione</span><span class="sxs-lookup"><span data-stu-id="2573b-175">Verify Export letter of credit</span></span>
1. <span data-ttu-id="2573b-176">Passare a Gestione cassa e banche > Lettere di credito > Lettera di credito di esportazione e pagamento all'importazione.</span><span class="sxs-lookup"><span data-stu-id="2573b-176">Go to Cash and bank management > Letters of credit > Export letter of credit and import collection.</span></span>
2. <span data-ttu-id="2573b-177">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="2573b-177">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="2573b-178">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2573b-178">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="2573b-179">Verificare che la lettera di credito di esportazione abbia lo stato della spedizione 'Fatturato'.</span><span class="sxs-lookup"><span data-stu-id="2573b-179">Verify that the Export letter of credit has a Shipment status of 'Invoiced'.</span></span>  

## <a name="customer-payment"></a><span data-ttu-id="2573b-180">Pagamento cliente</span><span class="sxs-lookup"><span data-stu-id="2573b-180">Customer payment</span></span>
1. <span data-ttu-id="2573b-181">Andare a Contabilità clienti > Pagamenti > Giornale di registrazione pagamenti.</span><span class="sxs-lookup"><span data-stu-id="2573b-181">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="2573b-182">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="2573b-182">Click New.</span></span>
3. <span data-ttu-id="2573b-183">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2573b-183">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="2573b-184">Nel campo Nome fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="2573b-184">In the Name field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="2573b-185">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2573b-185">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="2573b-186">Fare clic su Righe.</span><span class="sxs-lookup"><span data-stu-id="2573b-186">Click Lines.</span></span>
7. <span data-ttu-id="2573b-187">Nel campo Data immettere una data.</span><span class="sxs-lookup"><span data-stu-id="2573b-187">In the Date field, enter a date.</span></span>
8. <span data-ttu-id="2573b-188">Nel campo Conto, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="2573b-188">In the Account field, specify the desired values.</span></span>
9. <span data-ttu-id="2573b-189">Fare clic su Liquidazione.</span><span class="sxs-lookup"><span data-stu-id="2573b-189">Click Settlement.</span></span>
10. <span data-ttu-id="2573b-190">Selezionare la casella di controllo sull'intestazione di Totali.</span><span class="sxs-lookup"><span data-stu-id="2573b-190">Select the check box on the header of Totals.</span></span>
    * <span data-ttu-id="2573b-191">Nota: impostare il campo Mostra su 'Lettera di credito'.</span><span class="sxs-lookup"><span data-stu-id="2573b-191">Note: Set the Show field to 'Letter of credit'.</span></span>  
11. <span data-ttu-id="2573b-192">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="2573b-192">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="2573b-193">Selezionare o deselezionare la casella di controllo Contrassegna.</span><span class="sxs-lookup"><span data-stu-id="2573b-193">Select or clear the Mark check box.</span></span>
13. <span data-ttu-id="2573b-194">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2573b-194">Click OK.</span></span>
14. <span data-ttu-id="2573b-195">Fare clic sulla scheda Pagamento.</span><span class="sxs-lookup"><span data-stu-id="2573b-195">Click the Payment tab.</span></span>
    * <span data-ttu-id="2573b-196">Verificare i dettagli del numero di spedizione e del numero di documento bancario</span><span class="sxs-lookup"><span data-stu-id="2573b-196">Verify Bank document number and Shipment number details</span></span>  
15. <span data-ttu-id="2573b-197">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="2573b-197">Click Post.</span></span>

## <a name="verify-export-letter-of-credit-after-payment"></a><span data-ttu-id="2573b-198">Verificare la lettera di credito di esportazione dopo il pagamento</span><span class="sxs-lookup"><span data-stu-id="2573b-198">Verify Export letter of credit after payment</span></span>
1. <span data-ttu-id="2573b-199">Passare a Gestione cassa e banche > Lettere di credito > Lettera di credito di esportazione e pagamento all'importazione.</span><span class="sxs-lookup"><span data-stu-id="2573b-199">Go to Cash and bank management > Letters of credit > Export letter of credit and import collection.</span></span>
2. <span data-ttu-id="2573b-200">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="2573b-200">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="2573b-201">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2573b-201">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="2573b-202">Verificare Stato spedizione = Pagamento ricevuto e importo saldo = 0,00.</span><span class="sxs-lookup"><span data-stu-id="2573b-202">Verify Shipment status = Payment received and balance amount = 0.00.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]