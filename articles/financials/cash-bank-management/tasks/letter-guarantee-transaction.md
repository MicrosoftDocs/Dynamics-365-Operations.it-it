--- 
title: Transazione lettera di garanzia
description: In questa procedura vengono descritti i passaggi per il processo della lettera di garanzia.
author: kweekley
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: Reasons, SalesTableListPage, SalesCreateOrder, SalesTable, BankLGRequestForm, BankLGRequestFormRequest, BankLGGuarantee, BankLGFormSubmitToBank, BankDocumentAgreementLineLookup, BankLGFormReceiveFromBank, LedgerJournalTable, LedgerJournalTransDaily, BankLGRequestFormGiveToBeneficiary, BankLGFormGiveToBeneficiary, BankLGRequestFormIncreaseValue, BankLGFormIncreaseValue, BankLGRequestFormLiquidate, BankLGFormLiquidate
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 3b15133106d751c28029862217427e47085044f4
ms.contentlocale: it-it
ms.lasthandoff: 09/11/2018

---
# <a name="letter-of-guarantee-transaction"></a><span data-ttu-id="c3a1c-103">Transazione lettera di garanzia</span><span class="sxs-lookup"><span data-stu-id="c3a1c-103">Letter of guarantee transaction</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c3a1c-104">In questa procedura vengono descritti i passaggi per il processo della lettera di garanzia.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-104">This procedure walks through the Letter of guarantee process.</span></span>



<span data-ttu-id="c3a1c-105">Completare le seguenti attività prima di eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="c3a1c-105">The following tasks must be complete before completing this procedure:</span></span>

- <span data-ttu-id="c3a1c-106">Impostare le linee di credito bancarie e i profili registrazione per una lettera di garanzia.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-106">Set up bank facilities and posting profiles for a letter of guarantee.</span></span>

- <span data-ttu-id="c3a1c-107">Creare un contratto per linea di credito bancaria per una lettera di garanzia.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-107">Create a bank facility agreement for a letter of guarantee.</span></span>



<span data-ttu-id="c3a1c-108">Questa procedura utilizza la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-108">This procedure uses the USMF demo company.</span></span>


## <a name="create-sales-order-with-letter-of-guarantee"></a><span data-ttu-id="c3a1c-109">Creare un ordine cliente con lettera di garanzia</span><span class="sxs-lookup"><span data-stu-id="c3a1c-109">Create Sales Order with Letter of Guarantee</span></span>
1. <span data-ttu-id="c3a1c-110">Andare a Contabilità clienti > Ordini > Tutti gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-110">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="c3a1c-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-111">Click New.</span></span>
3. <span data-ttu-id="c3a1c-112">Nel campo Conto cliente, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-112">In the Customer account field, enter or select a value.</span></span>
4. <span data-ttu-id="c3a1c-113">Espandere la sezione Generale.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-113">Expand the General section.</span></span>
5. <span data-ttu-id="c3a1c-114">Nel campo Sito immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-114">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="c3a1c-115">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-115">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="c3a1c-116">Nel campo Magazzino immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-116">In the Warehouse field, enter or select a value.</span></span>
8. <span data-ttu-id="c3a1c-117">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="c3a1c-118">Selezionare 'Lettera di garanzia' nel campo Tipo di documento bancario.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-118">In the Bank document type field, select 'Letter of guarantee'.</span></span>
10. <span data-ttu-id="c3a1c-119">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-119">Click OK.</span></span>
11. <span data-ttu-id="c3a1c-120">Nel campo Numero di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-120">In the Item number field, enter or select a value.</span></span>
12. <span data-ttu-id="c3a1c-121">Nel campo Prezzo unitario immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-121">In the Unit price field, enter a number.</span></span>
13. <span data-ttu-id="c3a1c-122">Espandere la sezione Dettagli riga.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-122">Expand the Line details section.</span></span>
14. <span data-ttu-id="c3a1c-123">Fare clic sulla scheda Consegna.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-123">Click the Delivery tab.</span></span>
    * <span data-ttu-id="c3a1c-124">Nota: selezionare Controllo data di consegna = Nessuno</span><span class="sxs-lookup"><span data-stu-id="c3a1c-124">Note: Select Delivery date control = None</span></span>  
15. <span data-ttu-id="c3a1c-125">Nel campo Data di spedizione richiesta immettere una data.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-125">In the Requested ship date field, enter a date.</span></span>
16. <span data-ttu-id="c3a1c-126">Nel campo Data di spedizione confermata immettere una data.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-126">In the Confirmed ship date field, enter a date.</span></span>

## <a name="process-letter-of-guaranteerequest"></a><span data-ttu-id="c3a1c-127">Elaborare la lettera di garanzia: Richiesta</span><span class="sxs-lookup"><span data-stu-id="c3a1c-127">Process letter of guarantee_Request</span></span>
1. <span data-ttu-id="c3a1c-128">Nel riquadro azioni, fare clic su Gestisci.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-128">On the Action Pane, click Manage.</span></span>
2. <span data-ttu-id="c3a1c-129">Fare clic su Lettera di garanzia.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-129">Click Letter of guarantee.</span></span>
3. <span data-ttu-id="c3a1c-130">Nel Riquadro azioni, fare clic su Lettera di garanzia.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-130">On the Action Pane, click Letter of guarantee.</span></span>
4. <span data-ttu-id="c3a1c-131">Fare clic su Richiesta per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-131">Click Request to open the drop dialog.</span></span>
5. <span data-ttu-id="c3a1c-132">Nel campo Tipo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-132">In the Type field, enter or select a value.</span></span>
6. <span data-ttu-id="c3a1c-133">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-133">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="c3a1c-134">Nel campo Valore immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-134">In the Value field, enter a number.</span></span>
8. <span data-ttu-id="c3a1c-135">Nel campo Data di scadenza immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-135">In the Expiration date field, enter a date and time.</span></span>
9. <span data-ttu-id="c3a1c-136">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-136">Click OK.</span></span>
10. <span data-ttu-id="c3a1c-137">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-137">Close the page.</span></span>

## <a name="process-letter-of-guaranteesubmit-to-bank"></a><span data-ttu-id="c3a1c-138">Elaborare la lettera di garanzia: Invia a banca</span><span class="sxs-lookup"><span data-stu-id="c3a1c-138">Process letter of guarantee_Submit to bank</span></span>
1. <span data-ttu-id="c3a1c-139">Fare clic su Gestione cassa e banche > Lettere di garanzia > Lettere di garanzia.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-139">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
2. <span data-ttu-id="c3a1c-140">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-140">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="c3a1c-141">Fare clic su Invia a banca per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-141">Click Submit to bank to open the drop dialog.</span></span>
4. <span data-ttu-id="c3a1c-142">Nel campo Conto bancario immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-142">In the Bank account field, enter or select a value.</span></span>
5. <span data-ttu-id="c3a1c-143">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-143">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="c3a1c-144">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-144">Click OK.</span></span>

## <a name="process-letter-of-guaranteereceive-from-bank"></a><span data-ttu-id="c3a1c-145">Elaborare la lettera di garanzia: Ricevi da banca</span><span class="sxs-lookup"><span data-stu-id="c3a1c-145">Process letter of guarantee_Receive from bank</span></span>
1. <span data-ttu-id="c3a1c-146">Fare clic su Ricevi da banca per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-146">Click Receive from bank to open the drop dialog.</span></span>
2. <span data-ttu-id="c3a1c-147">Digitare un valore nel campo Numero banca.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-147">In the Bank number field, type a value.</span></span>
    * <span data-ttu-id="c3a1c-148">Verificare i valori nei campi calcolati di spesa e margine.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-148">Verify the values in the calculated Margin and Expense fields.</span></span>  
3. <span data-ttu-id="c3a1c-149">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-149">Click OK.</span></span>
4. <span data-ttu-id="c3a1c-150">Espandere la sezione Azioni.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-150">Expand the Actions section.</span></span>
    * <span data-ttu-id="c3a1c-151">Verificare il record 'Ricevi da banca'.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-151">Verify the 'Receive from bank' record.</span></span>  
5. <span data-ttu-id="c3a1c-152">Fare clic per seguire il collegamento nel campo Numero batch giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-152">Click to follow the link in the Journal batch number field.</span></span>
6. <span data-ttu-id="c3a1c-153">Fare clic su Righe.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-153">Click Lines.</span></span>
    * <span data-ttu-id="c3a1c-154">Verificare la registrazione delle scritture contabili.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-154">Verify the posting of journal entries.</span></span>  
7. <span data-ttu-id="c3a1c-155">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-155">Close the page.</span></span>

## <a name="process-letter-of-guaranteegive-to-beneficiary"></a><span data-ttu-id="c3a1c-156">Elaborare la lettera di garanzia: Assegna al beneficiario</span><span class="sxs-lookup"><span data-stu-id="c3a1c-156">Process letter of guarantee_Give to beneficiary</span></span>
1. <span data-ttu-id="c3a1c-157">Andare a Contabilità clienti > Ordini > Tutti gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-157">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="c3a1c-158">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-158">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="c3a1c-159">Nel riquadro azioni, fare clic su Gestisci.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-159">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="c3a1c-160">Fare clic su Lettera di garanzia.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-160">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="c3a1c-161">Nel Riquadro azioni, fare clic su Lettera di garanzia.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-161">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="c3a1c-162">Fare clic su Assegna al beneficiario per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-162">Click Give to beneficiary to open the drop dialog.</span></span>
7. <span data-ttu-id="c3a1c-163">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-163">Click OK.</span></span>
8. <span data-ttu-id="c3a1c-164">Fare clic su Gestione cassa e banche > Lettere di garanzia > Lettere di garanzia.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-164">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
9. <span data-ttu-id="c3a1c-165">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-165">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="c3a1c-166">Fare clic su Assegna al beneficiario per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-166">Click Give to beneficiary to open the drop dialog.</span></span>
11. <span data-ttu-id="c3a1c-167">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-167">Click OK.</span></span>
12. <span data-ttu-id="c3a1c-168">Espandere la sezione Azioni.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-168">Expand the Actions section.</span></span>
    * <span data-ttu-id="c3a1c-169">Convalidare il record 'Assegna al beneficiario'.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-169">Validate the 'Give to beneficiary' record.</span></span>  

## <a name="process-letter-of-guaranteeincrease-value"></a><span data-ttu-id="c3a1c-170">Elaborare la lettera di garanzia: Aumenta valore</span><span class="sxs-lookup"><span data-stu-id="c3a1c-170">Process letter of guarantee_Increase value</span></span>
1. <span data-ttu-id="c3a1c-171">Andare a Contabilità clienti > Ordini > Tutti gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-171">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="c3a1c-172">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-172">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="c3a1c-173">Nel riquadro azioni, fare clic su Gestisci.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-173">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="c3a1c-174">Fare clic su Lettera di garanzia.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-174">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="c3a1c-175">Nel Riquadro azioni, fare clic su Lettera di garanzia.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-175">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="c3a1c-176">Fare clic su Aumenta valore per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-176">Click Increase value to open the drop dialog.</span></span>
7. <span data-ttu-id="c3a1c-177">Nel campo Valore da aggiungere immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-177">In the Value to add field, enter a number.</span></span>
8. <span data-ttu-id="c3a1c-178">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-178">Click OK.</span></span>
9. <span data-ttu-id="c3a1c-179">Fare clic su Gestione cassa e banche > Lettere di garanzia > Lettere di garanzia.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-179">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
10. <span data-ttu-id="c3a1c-180">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-180">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="c3a1c-181">Fare clic su Aumenta valore per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-181">Click Increase value to open the drop dialog.</span></span>
12. <span data-ttu-id="c3a1c-182">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-182">Click OK.</span></span>
13. <span data-ttu-id="c3a1c-183">Espandere la sezione Azioni.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-183">Expand the Actions section.</span></span>
    * <span data-ttu-id="c3a1c-184">Verificare il record 'Aumenta valore'.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-184">Verify the 'Increase value' record.</span></span>  
14. <span data-ttu-id="c3a1c-185">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-185">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="c3a1c-186">Fare clic per seguire il collegamento nel campo Numero batch giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-186">Click to follow the link in the Journal batch number field.</span></span>
16. <span data-ttu-id="c3a1c-187">Fare clic su Righe.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-187">Click Lines.</span></span>
    * <span data-ttu-id="c3a1c-188">Verificare la scritture contabili registrate.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-188">Verify the posted journal entries.</span></span>  

## <a name="process-letter-of-guaranteeliquidate"></a><span data-ttu-id="c3a1c-189">Elaborare la lettera di garanzia: Liquida</span><span class="sxs-lookup"><span data-stu-id="c3a1c-189">Process letter of guarantee_Liquidate</span></span>
1. <span data-ttu-id="c3a1c-190">Andare a Contabilità clienti > Ordini > Tutti gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-190">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="c3a1c-191">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-191">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="c3a1c-192">Nel riquadro azioni, fare clic su Gestisci.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-192">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="c3a1c-193">Fare clic su Lettera di garanzia.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-193">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="c3a1c-194">Nel Riquadro azioni, fare clic su Lettera di garanzia.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-194">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="c3a1c-195">Fare clic su Liquida per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-195">Click Liquidate to open the drop dialog.</span></span>
7. <span data-ttu-id="c3a1c-196">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-196">Click OK.</span></span>
8. <span data-ttu-id="c3a1c-197">Fare clic su Gestione cassa e banche > Lettere di garanzia > Lettere di garanzia.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-197">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
9. <span data-ttu-id="c3a1c-198">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-198">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="c3a1c-199">Fare clic su Liquida per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-199">Click Liquidate to open the drop dialog.</span></span>
11. <span data-ttu-id="c3a1c-200">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-200">Click OK.</span></span>
12. <span data-ttu-id="c3a1c-201">Espandere la sezione Azioni.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-201">Expand the Actions section.</span></span>
    * <span data-ttu-id="c3a1c-202">Verificare il record 'Liquida'.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-202">Verify the 'Liquidate' record.</span></span>  
13. <span data-ttu-id="c3a1c-203">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-203">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="c3a1c-204">Fare clic per seguire il collegamento nel campo Numero batch giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-204">Click to follow the link in the Journal batch number field.</span></span>
15. <span data-ttu-id="c3a1c-205">Fare clic su Righe.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-205">Click Lines.</span></span>
    * <span data-ttu-id="c3a1c-206">Verificare la scritture contabili registrate.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-206">Verify the posted journal entries.</span></span>  
16. <span data-ttu-id="c3a1c-207">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c3a1c-207">Close the page.</span></span>


