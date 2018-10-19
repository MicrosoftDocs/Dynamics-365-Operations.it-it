--- 
title: Importare la lettera di credito
description: In questa procedura vengono descritti i passaggi per importare una lettera di credito.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendTable, VendBankAccounts, PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, BankLCImport,  PurchEditLines, VendEditInvoice, SrsReportViewerForm, LedgerJournalTable, LedgerJournalTransVendPaym, VendOpenTrans, SysQueryForm, BankAccountTableLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: c1768494182a79d7a33044498c1e768e61d937d1
ms.contentlocale: it-it
ms.lasthandoff: 10/16/2018

---
# <a name="import-letter-of-credit"></a><span data-ttu-id="25009-103">Importare la lettera di credito</span><span class="sxs-lookup"><span data-stu-id="25009-103">Import letter of credit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="25009-104">In questa procedura vengono descritti i passaggi per importare una lettera di credito.</span><span class="sxs-lookup"><span data-stu-id="25009-104">This procedure walks through the process of importing a letter of credit.</span></span> <span data-ttu-id="25009-105">Prima di completare la procedura è necessario configurare quanto segue: le linee di credito bancarie, i profili registrazione, un contratto per linea di credito bancaria e i dettagli bancari del fornitore.</span><span class="sxs-lookup"><span data-stu-id="25009-105">The following must be set up before completing this procedure: bank facilities, posting profiles, a bank facility agreement and vendor bank details.</span></span>

<span data-ttu-id="25009-106">Questa procedura utilizza la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="25009-106">This procedure uses the USMF demo company.</span></span>


## <a name="create-a-purchase-order-with-letter-of-credit"></a><span data-ttu-id="25009-107">Creare un ordine acquisto con una lettera di credito</span><span class="sxs-lookup"><span data-stu-id="25009-107">Create a Purchase order with Letter of credit</span></span>
1. <span data-ttu-id="25009-108">Fare clic su Contabilità fornitori > Ordini fornitore > Tutti gli ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="25009-108">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="25009-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="25009-109">Click New.</span></span>
3. <span data-ttu-id="25009-110">Nel campo Conto fornitore, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="25009-110">In the Vendor account field, enter or select a value.</span></span>
4. <span data-ttu-id="25009-111">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="25009-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="25009-112">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="25009-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="25009-113">Espandere la sezione Generale.</span><span class="sxs-lookup"><span data-stu-id="25009-113">Expand the General section.</span></span>
7. <span data-ttu-id="25009-114">Nel campo Sito immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="25009-114">In the Site field, enter or select a value.</span></span>
8. <span data-ttu-id="25009-115">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="25009-115">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="25009-116">Nel campo Magazzino immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="25009-116">In the Warehouse field, enter or select a value.</span></span>
10. <span data-ttu-id="25009-117">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="25009-117">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="25009-118">Immettere una data nel campo Data di registrazione.</span><span class="sxs-lookup"><span data-stu-id="25009-118">In the Accounting date field, enter a date.</span></span>
12. <span data-ttu-id="25009-119">Immettere una data nel campo Data di consegna.</span><span class="sxs-lookup"><span data-stu-id="25009-119">In the Delivery date field, enter a date.</span></span>
    * <span data-ttu-id="25009-120">Nota: il campo 'Tipo di documento bancario' deve essere selezionato con il valore 'Lettera di credito'.</span><span class="sxs-lookup"><span data-stu-id="25009-120">Note: The 'Bank document type' field should be selected with the value  'Letter of credit'.</span></span>  
13. <span data-ttu-id="25009-121">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="25009-121">Click OK.</span></span>
14. <span data-ttu-id="25009-122">Nel campo Numero di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="25009-122">In the Item number field, enter or select a value.</span></span>
15. <span data-ttu-id="25009-123">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="25009-123">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="25009-124">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="25009-124">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="25009-125">Espandere la sezione Dettagli riga.</span><span class="sxs-lookup"><span data-stu-id="25009-125">Expand the Line details section.</span></span>
18. <span data-ttu-id="25009-126">Fare clic sulla scheda Consegna.</span><span class="sxs-lookup"><span data-stu-id="25009-126">Click the Delivery tab.</span></span>
19. <span data-ttu-id="25009-127">Immettere una data nel campo Data di consegna.</span><span class="sxs-lookup"><span data-stu-id="25009-127">In the Delivery date field, enter a date.</span></span>
20. <span data-ttu-id="25009-128">Immettere una data nel campo Data di consegna confermata.</span><span class="sxs-lookup"><span data-stu-id="25009-128">In the Confirmed delivery date field, enter a date.</span></span>
21. <span data-ttu-id="25009-129">Nel campo Prezzo unitario immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="25009-129">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="25009-130">Definire i dettagli della lettera di credito.</span><span class="sxs-lookup"><span data-stu-id="25009-130">Define the Letter of credit details.</span></span>  
22. <span data-ttu-id="25009-131">Nel riquadro azioni, fare clic su Gestisci.</span><span class="sxs-lookup"><span data-stu-id="25009-131">On the Action Pane, click Manage.</span></span>
23. <span data-ttu-id="25009-132">Fare clic su Lettera di credito/pagamento all'importazione.</span><span class="sxs-lookup"><span data-stu-id="25009-132">Click Letter of credit / import collection.</span></span>
24. <span data-ttu-id="25009-133">Nel campo Data richiesta immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="25009-133">In the Application date field, enter a date and time.</span></span>
    * <span data-ttu-id="25009-134">Verificare che il campo 'Conto bancario' contenga il conto bancario attivo predefinito in base alla data dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="25009-134">Verify that the 'Bank account' field has the default active Bank account, which is based on the application date.</span></span>  
25. <span data-ttu-id="25009-135">Digitare un valore nel campo Numero documento bancario.</span><span class="sxs-lookup"><span data-stu-id="25009-135">In the Bank document number field, type a value.</span></span>
26. <span data-ttu-id="25009-136">Nel campo Data ricevimento immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="25009-136">In the Date of receipt field, enter a date and time.</span></span>
27. <span data-ttu-id="25009-137">Espandere la sezione Documento bancario.</span><span class="sxs-lookup"><span data-stu-id="25009-137">Expand the Bank document section.</span></span>
28. <span data-ttu-id="25009-138">Nel campo Data di scadenza immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="25009-138">In the Expiration date field, enter a date and time.</span></span>
29. <span data-ttu-id="25009-139">Espandere la sezione Dettagli banca.</span><span class="sxs-lookup"><span data-stu-id="25009-139">Expand the Bank details section.</span></span>
30. <span data-ttu-id="25009-140">Nel campo Banca avvisante immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="25009-140">In the Advising bank field, enter or select a value.</span></span>
31. <span data-ttu-id="25009-141">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="25009-141">In the list, click the link in the selected row.</span></span>
32. <span data-ttu-id="25009-142">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="25009-142">Click Save.</span></span>
33. <span data-ttu-id="25009-143">Fare clic su Recupera spedizioni ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="25009-143">Click Fetch purchase order shipments.</span></span>
34. <span data-ttu-id="25009-144">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="25009-144">Close the page.</span></span>
35. <span data-ttu-id="25009-145">Nel riquadro azioni fare clic su Acquisti.</span><span class="sxs-lookup"><span data-stu-id="25009-145">On the Action Pane, click Purchase.</span></span>
36. <span data-ttu-id="25009-146">Fare clic su Conferma.</span><span class="sxs-lookup"><span data-stu-id="25009-146">Click Confirm.</span></span>
37. <span data-ttu-id="25009-147">Nel riquadro azioni, fare clic su Gestisci.</span><span class="sxs-lookup"><span data-stu-id="25009-147">On the Action Pane, click Manage.</span></span>
38. <span data-ttu-id="25009-148">Fare clic su Lettera di credito/pagamento all'importazione.</span><span class="sxs-lookup"><span data-stu-id="25009-148">Click Letter of credit / import collection.</span></span>
39. <span data-ttu-id="25009-149">Fare clic su Elabora.</span><span class="sxs-lookup"><span data-stu-id="25009-149">Click Process.</span></span>
40. <span data-ttu-id="25009-150">Fare clic su Conferma.</span><span class="sxs-lookup"><span data-stu-id="25009-150">Click Confirm.</span></span>
    * <span data-ttu-id="25009-151">Verificare che il saldo linea di credito riduca l'importo dell'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="25009-151">Verify that the Facility balance reduces the purchase order amount.</span></span>  <span data-ttu-id="25009-152">In questo esempio, Importo acquisto = 500,00, Limite struttura = 10000,00, pertanto, Saldo linea di credito = 9500,00.</span><span class="sxs-lookup"><span data-stu-id="25009-152">In this example, Purchase amount = 500.00,  Facility limit = 10000.00,  therefore, Facility balance = 9500.00.</span></span>  
41. <span data-ttu-id="25009-153">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="25009-153">Close the page.</span></span>
42. <span data-ttu-id="25009-154">Nel campo Prezzo unitario immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="25009-154">In the Unit price field, enter a number.</span></span>
43. <span data-ttu-id="25009-155">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="25009-155">Click Save.</span></span>
44. <span data-ttu-id="25009-156">Nel riquadro azioni fare clic su Acquisti.</span><span class="sxs-lookup"><span data-stu-id="25009-156">On the Action Pane, click Purchase.</span></span>
45. <span data-ttu-id="25009-157">Fare clic su Conferma.</span><span class="sxs-lookup"><span data-stu-id="25009-157">Click Confirm.</span></span>
    * <span data-ttu-id="25009-158">Modificare la lettera di credito, a causa della modifica del prezzo unitario.</span><span class="sxs-lookup"><span data-stu-id="25009-158">Amend the Letter of credit, due to the change in Unit price.</span></span>  
46. <span data-ttu-id="25009-159">Nel riquadro azioni, fare clic su Gestisci.</span><span class="sxs-lookup"><span data-stu-id="25009-159">On the Action Pane, click Manage.</span></span>
47. <span data-ttu-id="25009-160">Fare clic su Lettera di credito/pagamento all'importazione.</span><span class="sxs-lookup"><span data-stu-id="25009-160">Click Letter of credit / import collection.</span></span>
    * <span data-ttu-id="25009-161">Modificare la lettera di credito, a causa della modifica del prezzo unitario di acquisto.</span><span class="sxs-lookup"><span data-stu-id="25009-161">Amend the letter of credit, due to the change in Purchase unit price.</span></span>  
48. <span data-ttu-id="25009-162">Fare clic su Elabora.</span><span class="sxs-lookup"><span data-stu-id="25009-162">Click Process.</span></span>
49. <span data-ttu-id="25009-163">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="25009-163">Click Amend.</span></span>
50. <span data-ttu-id="25009-164">Fare clic su Rimuovi.</span><span class="sxs-lookup"><span data-stu-id="25009-164">Click Remove.</span></span>
51. <span data-ttu-id="25009-165">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="25009-165">Click Yes.</span></span>
52. <span data-ttu-id="25009-166">Fare clic su Recupera spedizioni ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="25009-166">Click Fetch purchase order shipments.</span></span>
53. <span data-ttu-id="25009-167">Fare clic su Elabora.</span><span class="sxs-lookup"><span data-stu-id="25009-167">Click Process.</span></span>
54. <span data-ttu-id="25009-168">Fare clic su Conferma.</span><span class="sxs-lookup"><span data-stu-id="25009-168">Click Confirm.</span></span>
    * <span data-ttu-id="25009-169">Verificare che il saldo linea di credito riduca l'importo dell'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="25009-169">Verify that the Facility balance reduces the purchase order amount.</span></span>  <span data-ttu-id="25009-170">In questo esempio, è stato modificato Importo acquisto = 600,00, Limite struttura = 10000,00, pertanto, Saldo linea di credito = 9400,00.</span><span class="sxs-lookup"><span data-stu-id="25009-170">In this example, edited Purchase amount = 600.00,  Facility limit = 10000.00,  therefore, Facility balance = 9400.00.</span></span>  
55. <span data-ttu-id="25009-171">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="25009-171">Close the page.</span></span>

## <a name="post-packing-slip"></a><span data-ttu-id="25009-172">Registrare il documento di trasporto</span><span class="sxs-lookup"><span data-stu-id="25009-172">Post Packing slip</span></span>
1. <span data-ttu-id="25009-173">Nel riquadro azioni fare clic su Ricevimento.</span><span class="sxs-lookup"><span data-stu-id="25009-173">On the Action Pane, click Receive.</span></span>
2. <span data-ttu-id="25009-174">Fare clic su Entrata prodotti.</span><span class="sxs-lookup"><span data-stu-id="25009-174">Click Product receipt.</span></span>
3. <span data-ttu-id="25009-175">Digitare un valore nel campo PurchParmTable_Num.</span><span class="sxs-lookup"><span data-stu-id="25009-175">In the PurchParmTable_Num field, type a value.</span></span>
    * <span data-ttu-id="25009-176">Selezionare il numero di spedizione creato in riferimento alla lettera di credito.</span><span class="sxs-lookup"><span data-stu-id="25009-176">Select the Shipment number created with reference to the Letter of credit.</span></span>  
4. <span data-ttu-id="25009-177">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="25009-177">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="25009-178">Nel campo Data entrata prodotti immettere una data.</span><span class="sxs-lookup"><span data-stu-id="25009-178">In the Product receipt date field, enter a date.</span></span>
6. <span data-ttu-id="25009-179">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="25009-179">Click OK.</span></span>
7. <span data-ttu-id="25009-180">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="25009-180">Close the page.</span></span>
8. <span data-ttu-id="25009-181">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="25009-181">Close the page.</span></span>

## <a name="verify-import-letter-of-credit-status"></a><span data-ttu-id="25009-182">Verificare lo stato dell'importazione della lettera di credito</span><span class="sxs-lookup"><span data-stu-id="25009-182">Verify Import letter of credit status</span></span>
1. <span data-ttu-id="25009-183">Passare a Gestione cassa e banche > Lettere di credito > Lettera di credito di importazione e pagamento all'importazione.</span><span class="sxs-lookup"><span data-stu-id="25009-183">Go to Cash and bank management > Letters of credit > Import letter of credit and import collection.</span></span>
2. <span data-ttu-id="25009-184">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="25009-184">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="25009-185">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="25009-185">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="25009-186">Verificare lo stato dell'importazione della lettera di credito.</span><span class="sxs-lookup"><span data-stu-id="25009-186">Verify the Import letter of credit status.</span></span>    
    *   
4. <span data-ttu-id="25009-187">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="25009-187">Close the page.</span></span>
5. <span data-ttu-id="25009-188">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="25009-188">Close the page.</span></span>

## <a name="post-purchase-invoice"></a><span data-ttu-id="25009-189">Registrare la fattura di acquisto</span><span class="sxs-lookup"><span data-stu-id="25009-189">Post purchase invoice</span></span>
1. <span data-ttu-id="25009-190">Fare clic su Contabilità fornitori > Ordini fornitore > Tutti gli ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="25009-190">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
    * <span data-ttu-id="25009-191">Selezionare l'ordine fornitore creato con la lettera di credito.</span><span class="sxs-lookup"><span data-stu-id="25009-191">Select the purchase order that was created with letter of credit.</span></span>  
2. <span data-ttu-id="25009-192">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="25009-192">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="25009-193">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="25009-193">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="25009-194">Nel riquadro azioni fare clic su Fattura.</span><span class="sxs-lookup"><span data-stu-id="25009-194">On the Action Pane, click Invoice.</span></span>
5. <span data-ttu-id="25009-195">Fare clic su Fattura.</span><span class="sxs-lookup"><span data-stu-id="25009-195">Click Invoice.</span></span>
6. <span data-ttu-id="25009-196">Digitare un valore nel campo Numero.</span><span class="sxs-lookup"><span data-stu-id="25009-196">In the Number field, type a value.</span></span>
7. <span data-ttu-id="25009-197">Nel campo Numero spedizione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="25009-197">In the Shipment number field, enter or select a value.</span></span>
8. <span data-ttu-id="25009-198">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="25009-198">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="25009-199">Immettere una data nel campo Data fattura.</span><span class="sxs-lookup"><span data-stu-id="25009-199">In the Invoice date field, enter a date.</span></span>
10. <span data-ttu-id="25009-200">Fare clic su Aggiorna stato di abbinamento.</span><span class="sxs-lookup"><span data-stu-id="25009-200">Click Update match status.</span></span>
11. <span data-ttu-id="25009-201">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="25009-201">Click Post.</span></span>
12. <span data-ttu-id="25009-202">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="25009-202">Close the page.</span></span>
13. <span data-ttu-id="25009-203">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="25009-203">Close the page.</span></span>

## <a name="verify-import-letter-of-credit-status"></a><span data-ttu-id="25009-204">Verificare lo stato dell'importazione della lettera di credito</span><span class="sxs-lookup"><span data-stu-id="25009-204">Verify Import letter of credit status</span></span>
1. <span data-ttu-id="25009-205">Passare a Gestione cassa e banche > Lettere di credito > Lettera di credito di importazione e pagamento all'importazione.</span><span class="sxs-lookup"><span data-stu-id="25009-205">Go to Cash and bank management > Letters of credit > Import letter of credit and import collection.</span></span>
2. <span data-ttu-id="25009-206">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="25009-206">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="25009-207">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="25009-207">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="25009-208">Verificare l'importazione della lettera di credito.</span><span class="sxs-lookup"><span data-stu-id="25009-208">Verify the Import letter of credit2.</span></span>  
    * <span data-ttu-id="25009-209">Convalida : stato della spedizione = dettagli fatturati di linea di credito bancaria</span><span class="sxs-lookup"><span data-stu-id="25009-209">Validate :  Shipment status = Invoiced  Bank facility details</span></span>  
4. <span data-ttu-id="25009-210">Fare clic su Visualizza.</span><span class="sxs-lookup"><span data-stu-id="25009-210">Click View.</span></span>
5. <span data-ttu-id="25009-211">Fare clic su Stampa richiesta.</span><span class="sxs-lookup"><span data-stu-id="25009-211">Click Print application.</span></span>
6. <span data-ttu-id="25009-212">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="25009-212">Click OK.</span></span>
    * <span data-ttu-id="25009-213">Verificare che la richiesta di lettera di credito venga stampata.</span><span class="sxs-lookup"><span data-stu-id="25009-213">Verify that the Letter of credit application gets printed.</span></span>  
7. <span data-ttu-id="25009-214">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="25009-214">Close the page.</span></span>
8. <span data-ttu-id="25009-215">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="25009-215">Close the page.</span></span>
9. <span data-ttu-id="25009-216">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="25009-216">Close the page.</span></span>

## <a name="post-vendor-payment-journal-for-the-created-purchase-invoice-with-letter-of-credit"></a><span data-ttu-id="25009-217">Registrare il giornale di registrazione pagamenti fornitore per la fattura di acquisto creata con la lettera di credito</span><span class="sxs-lookup"><span data-stu-id="25009-217">Post Vendor payment journal for the created purchase invoice with letter of credit</span></span>
1. <span data-ttu-id="25009-218">Andare a Contabilità fornitori > Pagamenti > Giornale di registrazione pagamenti.</span><span class="sxs-lookup"><span data-stu-id="25009-218">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="25009-219">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="25009-219">Click New.</span></span>
3. <span data-ttu-id="25009-220">Nel campo Nome immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="25009-220">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="25009-221">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="25009-221">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="25009-222">Fare clic su Righe.</span><span class="sxs-lookup"><span data-stu-id="25009-222">Click Lines.</span></span>
6. <span data-ttu-id="25009-223">Nel campo Data immettere una data.</span><span class="sxs-lookup"><span data-stu-id="25009-223">In the Date field, enter a date.</span></span>
7. <span data-ttu-id="25009-224">Nel campo Conto, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="25009-224">In the Account field, specify the desired values.</span></span>
8. <span data-ttu-id="25009-225">Fare clic su Liquida transazioni.</span><span class="sxs-lookup"><span data-stu-id="25009-225">Click Settle transactions.</span></span>
9. <span data-ttu-id="25009-226">Espandere la sezione Totali.</span><span class="sxs-lookup"><span data-stu-id="25009-226">Expand the Totals section.</span></span>
10. <span data-ttu-id="25009-227">Selezionare un'opzione nel campo Mostra.</span><span class="sxs-lookup"><span data-stu-id="25009-227">In the Show field, select an option.</span></span>
    * <span data-ttu-id="25009-228">Verificare che i campi Numero documento bancario e Numero spedizione siano stati aggiornati.</span><span class="sxs-lookup"><span data-stu-id="25009-228">Verify that the Bank document number and Shipment number fields have been updated.</span></span>  
11. <span data-ttu-id="25009-229">Selezionare la casella di controllo Contrassegna.</span><span class="sxs-lookup"><span data-stu-id="25009-229">Select the Mark check box.</span></span>
12. <span data-ttu-id="25009-230">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="25009-230">Click OK.</span></span>
13. <span data-ttu-id="25009-231">Fare clic sulla scheda Pagamento.</span><span class="sxs-lookup"><span data-stu-id="25009-231">Click the Payment tab.</span></span>
    * <span data-ttu-id="25009-232">Verificare che i campi Numero documento bancario e Numero spedizione siano stati aggiornati.</span><span class="sxs-lookup"><span data-stu-id="25009-232">Verify that the Bank document number and Shipment number fields have been updated.</span></span>  
14. <span data-ttu-id="25009-233">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="25009-233">Click Post.</span></span>
15. <span data-ttu-id="25009-234">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="25009-234">Close the page.</span></span>
16. <span data-ttu-id="25009-235">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="25009-235">Close the page.</span></span>

## <a name="verify-import-letter-of-credit-status-after-invoice-paid"></a><span data-ttu-id="25009-236">Verificare lo stato della lettera di credito di importazione dopo la fattura pagata</span><span class="sxs-lookup"><span data-stu-id="25009-236">Verify Import letter of credit status after Invoice paid</span></span>
1. <span data-ttu-id="25009-237">Passare a Gestione cassa e banche > Lettere di credito > Lettera di credito di importazione e pagamento all'importazione.</span><span class="sxs-lookup"><span data-stu-id="25009-237">Go to Cash and bank management > Letters of credit > Import letter of credit and import collection.</span></span>
2. <span data-ttu-id="25009-238">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="25009-238">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="25009-239">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="25009-239">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="25009-240">Verificare lo stato dell'importazione della lettera di credito.</span><span class="sxs-lookup"><span data-stu-id="25009-240">Verify the Import letter of credit status.</span></span>   
4. <span data-ttu-id="25009-241">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="25009-241">Close the page.</span></span>

## <a name="verify-the-bank-facility-limit-and-utilization-report"></a><span data-ttu-id="25009-242">Verificare il report di utilizzo e limite di linee di credito bancarie</span><span class="sxs-lookup"><span data-stu-id="25009-242">Verify the Bank facility limit and utilization report</span></span>
1. <span data-ttu-id="25009-243">Passare a Gestione cassa e banche > Richieste di informazioni e report Lettere di credito o garanzia > Report di utilizzo e linee di credito bancarie.</span><span class="sxs-lookup"><span data-stu-id="25009-243">Go to Cash and bank management > Inquiries and reports > Letters of credit or guarantee > Bank facilities and utilization report.</span></span>
2. <span data-ttu-id="25009-244">Espandere la sezione Record da includere.</span><span class="sxs-lookup"><span data-stu-id="25009-244">Expand the Records to include section.</span></span>
3. <span data-ttu-id="25009-245">Fare clic su Filtro.</span><span class="sxs-lookup"><span data-stu-id="25009-245">Click Filter.</span></span>
    * <span data-ttu-id="25009-246">Definire il campo Criteri con il conto bancario richiesto.</span><span class="sxs-lookup"><span data-stu-id="25009-246">Define the Criteria field with the required bank account.</span></span>  
4. <span data-ttu-id="25009-247">Nel campo Criteri immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="25009-247">In the Criteria field, enter or select a value.</span></span>
5. <span data-ttu-id="25009-248">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="25009-248">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="25009-249">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="25009-249">Click OK.</span></span>
7. <span data-ttu-id="25009-250">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="25009-250">Click OK.</span></span>
    * <span data-ttu-id="25009-251">Verificare il report con l'elenco delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="25009-251">Verify the report which lists the transactions.</span></span>  
    * <span data-ttu-id="25009-252">Verificare che il report elenchi le transazioni con il numero di documento bancario, il limite struttura, l'importo utilizzato e l'importo del saldo linea di credito.</span><span class="sxs-lookup"><span data-stu-id="25009-252">Verify the report lists the transactions with Bank document number, Facility limit, utilized amount and the facility balance amount.</span></span>  
8. <span data-ttu-id="25009-253">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="25009-253">Close the page.</span></span>


