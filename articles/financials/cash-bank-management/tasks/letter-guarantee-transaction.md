---
title: Transazione lettera di garanzia
description: In questa procedura vengono descritti i passaggi per il processo della lettera di garanzia.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Reasons, SalesTableListPage, SalesCreateOrder, SalesTable, BankLGRequestForm, BankLGRequestFormRequest, BankLGGuarantee, BankLGFormSubmitToBank, BankDocumentAgreementLineLookup, BankLGFormReceiveFromBank, LedgerJournalTable, LedgerJournalTransDaily, BankLGRequestFormGiveToBeneficiary, BankLGFormGiveToBeneficiary, BankLGRequestFormIncreaseValue, BankLGFormIncreaseValue, BankLGRequestFormLiquidate, BankLGFormLiquidate
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4dc6ee178121fae05d538f5103919442d91e65eb
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1566112"
---
# <a name="letter-of-guarantee-transaction"></a><span data-ttu-id="4952e-103">Transazione lettera di garanzia</span><span class="sxs-lookup"><span data-stu-id="4952e-103">Letter of guarantee transaction</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4952e-104">In questa procedura vengono descritti i passaggi per il processo della lettera di garanzia.</span><span class="sxs-lookup"><span data-stu-id="4952e-104">This procedure walks through the Letter of guarantee process.</span></span>



<span data-ttu-id="4952e-105">Completare le seguenti attività prima di eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="4952e-105">The following tasks must be complete before completing this procedure:</span></span>

- <span data-ttu-id="4952e-106">Impostare le linee di credito bancarie e i profili registrazione per una lettera di garanzia.</span><span class="sxs-lookup"><span data-stu-id="4952e-106">Set up bank facilities and posting profiles for a letter of guarantee.</span></span>

- <span data-ttu-id="4952e-107">Creare un contratto per linea di credito bancaria per una lettera di garanzia.</span><span class="sxs-lookup"><span data-stu-id="4952e-107">Create a bank facility agreement for a letter of guarantee.</span></span>



<span data-ttu-id="4952e-108">Questa procedura utilizza la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="4952e-108">This procedure uses the USMF demo company.</span></span>


## <a name="create-sales-order-with-letter-of-guarantee"></a><span data-ttu-id="4952e-109">Creare un ordine cliente con lettera di garanzia</span><span class="sxs-lookup"><span data-stu-id="4952e-109">Create Sales Order with Letter of Guarantee</span></span>
1. <span data-ttu-id="4952e-110">Andare a Contabilità clienti > Ordini > Tutti gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="4952e-110">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="4952e-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="4952e-111">Click New.</span></span>
3. <span data-ttu-id="4952e-112">Nel campo Conto cliente, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4952e-112">In the Customer account field, enter or select a value.</span></span>
4. <span data-ttu-id="4952e-113">Espandere la sezione Generale.</span><span class="sxs-lookup"><span data-stu-id="4952e-113">Expand the General section.</span></span>
5. <span data-ttu-id="4952e-114">Nel campo Sito immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4952e-114">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="4952e-115">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="4952e-115">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="4952e-116">Nel campo Magazzino immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4952e-116">In the Warehouse field, enter or select a value.</span></span>
8. <span data-ttu-id="4952e-117">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="4952e-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="4952e-118">Selezionare 'Lettera di garanzia' nel campo Tipo di documento bancario.</span><span class="sxs-lookup"><span data-stu-id="4952e-118">In the Bank document type field, select 'Letter of guarantee'.</span></span>
10. <span data-ttu-id="4952e-119">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="4952e-119">Click OK.</span></span>
11. <span data-ttu-id="4952e-120">Nel campo Numero di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4952e-120">In the Item number field, enter or select a value.</span></span>
12. <span data-ttu-id="4952e-121">Nel campo Prezzo unitario immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="4952e-121">In the Unit price field, enter a number.</span></span>
13. <span data-ttu-id="4952e-122">Espandere la sezione Dettagli riga.</span><span class="sxs-lookup"><span data-stu-id="4952e-122">Expand the Line details section.</span></span>
14. <span data-ttu-id="4952e-123">Fare clic sulla scheda Consegna.</span><span class="sxs-lookup"><span data-stu-id="4952e-123">Click the Delivery tab.</span></span>
    * <span data-ttu-id="4952e-124">Nota: selezionare Controllo data di consegna = Nessuno</span><span class="sxs-lookup"><span data-stu-id="4952e-124">Note: Select Delivery date control = None</span></span>  
15. <span data-ttu-id="4952e-125">Nel campo Data di spedizione richiesta immettere una data.</span><span class="sxs-lookup"><span data-stu-id="4952e-125">In the Requested ship date field, enter a date.</span></span>
16. <span data-ttu-id="4952e-126">Nel campo Data di spedizione confermata immettere una data.</span><span class="sxs-lookup"><span data-stu-id="4952e-126">In the Confirmed ship date field, enter a date.</span></span>

## <a name="process-letter-of-guaranteerequest"></a><span data-ttu-id="4952e-127">Elaborare la lettera di garanzia: Richiesta</span><span class="sxs-lookup"><span data-stu-id="4952e-127">Process letter of guarantee_Request</span></span>
1. <span data-ttu-id="4952e-128">Nel riquadro azioni, fare clic su Gestisci.</span><span class="sxs-lookup"><span data-stu-id="4952e-128">On the Action Pane, click Manage.</span></span>
2. <span data-ttu-id="4952e-129">Fare clic su Lettera di garanzia.</span><span class="sxs-lookup"><span data-stu-id="4952e-129">Click Letter of guarantee.</span></span>
3. <span data-ttu-id="4952e-130">Nel Riquadro azioni, fare clic su Lettera di garanzia.</span><span class="sxs-lookup"><span data-stu-id="4952e-130">On the Action Pane, click Letter of guarantee.</span></span>
4. <span data-ttu-id="4952e-131">Fare clic su Richiesta per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="4952e-131">Click Request to open the drop dialog.</span></span>
5. <span data-ttu-id="4952e-132">Nel campo Tipo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4952e-132">In the Type field, enter or select a value.</span></span>
6. <span data-ttu-id="4952e-133">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="4952e-133">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="4952e-134">Nel campo Valore immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="4952e-134">In the Value field, enter a number.</span></span>
8. <span data-ttu-id="4952e-135">Nel campo Data di scadenza immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="4952e-135">In the Expiration date field, enter a date and time.</span></span>
9. <span data-ttu-id="4952e-136">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="4952e-136">Click OK.</span></span>
10. <span data-ttu-id="4952e-137">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4952e-137">Close the page.</span></span>

## <a name="process-letter-of-guaranteesubmit-to-bank"></a><span data-ttu-id="4952e-138">Elaborare la lettera di garanzia: Invia a banca</span><span class="sxs-lookup"><span data-stu-id="4952e-138">Process letter of guarantee_Submit to bank</span></span>
1. <span data-ttu-id="4952e-139">Fare clic su Gestione cassa e banche > Lettere di garanzia > Lettere di garanzia.</span><span class="sxs-lookup"><span data-stu-id="4952e-139">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
2. <span data-ttu-id="4952e-140">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="4952e-140">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="4952e-141">Fare clic su Invia a banca per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="4952e-141">Click Submit to bank to open the drop dialog.</span></span>
4. <span data-ttu-id="4952e-142">Nel campo Conto bancario immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4952e-142">In the Bank account field, enter or select a value.</span></span>
5. <span data-ttu-id="4952e-143">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="4952e-143">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="4952e-144">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="4952e-144">Click OK.</span></span>

## <a name="process-letter-of-guaranteereceive-from-bank"></a><span data-ttu-id="4952e-145">Elaborare la lettera di garanzia: Ricevi da banca</span><span class="sxs-lookup"><span data-stu-id="4952e-145">Process letter of guarantee_Receive from bank</span></span>
1. <span data-ttu-id="4952e-146">Fare clic su Ricevi da banca per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="4952e-146">Click Receive from bank to open the drop dialog.</span></span>
2. <span data-ttu-id="4952e-147">Digitare un valore nel campo Numero banca.</span><span class="sxs-lookup"><span data-stu-id="4952e-147">In the Bank number field, type a value.</span></span>
    * <span data-ttu-id="4952e-148">Verificare i valori nei campi calcolati di spesa e margine.</span><span class="sxs-lookup"><span data-stu-id="4952e-148">Verify the values in the calculated Margin and Expense fields.</span></span>  
3. <span data-ttu-id="4952e-149">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="4952e-149">Click OK.</span></span>
4. <span data-ttu-id="4952e-150">Espandere la sezione Azioni.</span><span class="sxs-lookup"><span data-stu-id="4952e-150">Expand the Actions section.</span></span>
    * <span data-ttu-id="4952e-151">Verificare il record 'Ricevi da banca'.</span><span class="sxs-lookup"><span data-stu-id="4952e-151">Verify the 'Receive from bank' record.</span></span>  
5. <span data-ttu-id="4952e-152">Fare clic per seguire il collegamento nel campo Numero batch giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="4952e-152">Click to follow the link in the Journal batch number field.</span></span>
6. <span data-ttu-id="4952e-153">Fare clic su Righe.</span><span class="sxs-lookup"><span data-stu-id="4952e-153">Click Lines.</span></span>
    * <span data-ttu-id="4952e-154">Verificare la registrazione delle scritture contabili.</span><span class="sxs-lookup"><span data-stu-id="4952e-154">Verify the posting of journal entries.</span></span>  
7. <span data-ttu-id="4952e-155">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4952e-155">Close the page.</span></span>

## <a name="process-letter-of-guaranteegive-to-beneficiary"></a><span data-ttu-id="4952e-156">Elaborare la lettera di garanzia: Assegna al beneficiario</span><span class="sxs-lookup"><span data-stu-id="4952e-156">Process letter of guarantee_Give to beneficiary</span></span>
1. <span data-ttu-id="4952e-157">Andare a Contabilità clienti > Ordini > Tutti gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="4952e-157">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="4952e-158">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="4952e-158">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="4952e-159">Nel riquadro azioni, fare clic su Gestisci.</span><span class="sxs-lookup"><span data-stu-id="4952e-159">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="4952e-160">Fare clic su Lettera di garanzia.</span><span class="sxs-lookup"><span data-stu-id="4952e-160">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="4952e-161">Nel Riquadro azioni, fare clic su Lettera di garanzia.</span><span class="sxs-lookup"><span data-stu-id="4952e-161">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="4952e-162">Fare clic su Assegna al beneficiario per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="4952e-162">Click Give to beneficiary to open the drop dialog.</span></span>
7. <span data-ttu-id="4952e-163">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="4952e-163">Click OK.</span></span>
8. <span data-ttu-id="4952e-164">Fare clic su Gestione cassa e banche > Lettere di garanzia > Lettere di garanzia.</span><span class="sxs-lookup"><span data-stu-id="4952e-164">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
9. <span data-ttu-id="4952e-165">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="4952e-165">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="4952e-166">Fare clic su Assegna al beneficiario per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="4952e-166">Click Give to beneficiary to open the drop dialog.</span></span>
11. <span data-ttu-id="4952e-167">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="4952e-167">Click OK.</span></span>
12. <span data-ttu-id="4952e-168">Espandere la sezione Azioni.</span><span class="sxs-lookup"><span data-stu-id="4952e-168">Expand the Actions section.</span></span>
    * <span data-ttu-id="4952e-169">Convalidare il record 'Assegna al beneficiario'.</span><span class="sxs-lookup"><span data-stu-id="4952e-169">Validate the 'Give to beneficiary' record.</span></span>  

## <a name="process-letter-of-guaranteeincrease-value"></a><span data-ttu-id="4952e-170">Elaborare la lettera di garanzia: Aumenta valore</span><span class="sxs-lookup"><span data-stu-id="4952e-170">Process letter of guarantee_Increase value</span></span>
1. <span data-ttu-id="4952e-171">Andare a Contabilità clienti > Ordini > Tutti gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="4952e-171">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="4952e-172">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="4952e-172">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="4952e-173">Nel riquadro azioni, fare clic su Gestisci.</span><span class="sxs-lookup"><span data-stu-id="4952e-173">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="4952e-174">Fare clic su Lettera di garanzia.</span><span class="sxs-lookup"><span data-stu-id="4952e-174">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="4952e-175">Nel Riquadro azioni, fare clic su Lettera di garanzia.</span><span class="sxs-lookup"><span data-stu-id="4952e-175">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="4952e-176">Fare clic su Aumenta valore per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="4952e-176">Click Increase value to open the drop dialog.</span></span>
7. <span data-ttu-id="4952e-177">Nel campo Valore da aggiungere immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="4952e-177">In the Value to add field, enter a number.</span></span>
8. <span data-ttu-id="4952e-178">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="4952e-178">Click OK.</span></span>
9. <span data-ttu-id="4952e-179">Fare clic su Gestione cassa e banche > Lettere di garanzia > Lettere di garanzia.</span><span class="sxs-lookup"><span data-stu-id="4952e-179">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
10. <span data-ttu-id="4952e-180">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="4952e-180">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="4952e-181">Fare clic su Aumenta valore per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="4952e-181">Click Increase value to open the drop dialog.</span></span>
12. <span data-ttu-id="4952e-182">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="4952e-182">Click OK.</span></span>
13. <span data-ttu-id="4952e-183">Espandere la sezione Azioni.</span><span class="sxs-lookup"><span data-stu-id="4952e-183">Expand the Actions section.</span></span>
    * <span data-ttu-id="4952e-184">Verificare il record 'Aumenta valore'.</span><span class="sxs-lookup"><span data-stu-id="4952e-184">Verify the 'Increase value' record.</span></span>  
14. <span data-ttu-id="4952e-185">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="4952e-185">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="4952e-186">Fare clic per seguire il collegamento nel campo Numero batch giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="4952e-186">Click to follow the link in the Journal batch number field.</span></span>
16. <span data-ttu-id="4952e-187">Fare clic su Righe.</span><span class="sxs-lookup"><span data-stu-id="4952e-187">Click Lines.</span></span>
    * <span data-ttu-id="4952e-188">Verificare la scritture contabili registrate.</span><span class="sxs-lookup"><span data-stu-id="4952e-188">Verify the posted journal entries.</span></span>  

## <a name="process-letter-of-guaranteeliquidate"></a><span data-ttu-id="4952e-189">Elaborare la lettera di garanzia: Liquida</span><span class="sxs-lookup"><span data-stu-id="4952e-189">Process letter of guarantee_Liquidate</span></span>
1. <span data-ttu-id="4952e-190">Andare a Contabilità clienti > Ordini > Tutti gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="4952e-190">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="4952e-191">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="4952e-191">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="4952e-192">Nel riquadro azioni, fare clic su Gestisci.</span><span class="sxs-lookup"><span data-stu-id="4952e-192">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="4952e-193">Fare clic su Lettera di garanzia.</span><span class="sxs-lookup"><span data-stu-id="4952e-193">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="4952e-194">Nel Riquadro azioni, fare clic su Lettera di garanzia.</span><span class="sxs-lookup"><span data-stu-id="4952e-194">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="4952e-195">Fare clic su Liquida per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="4952e-195">Click Liquidate to open the drop dialog.</span></span>
7. <span data-ttu-id="4952e-196">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="4952e-196">Click OK.</span></span>
8. <span data-ttu-id="4952e-197">Fare clic su Gestione cassa e banche > Lettere di garanzia > Lettere di garanzia.</span><span class="sxs-lookup"><span data-stu-id="4952e-197">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
9. <span data-ttu-id="4952e-198">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="4952e-198">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="4952e-199">Fare clic su Liquida per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="4952e-199">Click Liquidate to open the drop dialog.</span></span>
11. <span data-ttu-id="4952e-200">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="4952e-200">Click OK.</span></span>
12. <span data-ttu-id="4952e-201">Espandere la sezione Azioni.</span><span class="sxs-lookup"><span data-stu-id="4952e-201">Expand the Actions section.</span></span>
    * <span data-ttu-id="4952e-202">Verificare il record 'Liquida'.</span><span class="sxs-lookup"><span data-stu-id="4952e-202">Verify the 'Liquidate' record.</span></span>  
13. <span data-ttu-id="4952e-203">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="4952e-203">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="4952e-204">Fare clic per seguire il collegamento nel campo Numero batch giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="4952e-204">Click to follow the link in the Journal batch number field.</span></span>
15. <span data-ttu-id="4952e-205">Fare clic su Righe.</span><span class="sxs-lookup"><span data-stu-id="4952e-205">Click Lines.</span></span>
    * <span data-ttu-id="4952e-206">Verificare la scritture contabili registrate.</span><span class="sxs-lookup"><span data-stu-id="4952e-206">Verify the posted journal entries.</span></span>  
16. <span data-ttu-id="4952e-207">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4952e-207">Close the page.</span></span>

