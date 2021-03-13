---
title: Definire i mapping di modello ER e selezionare le relative origini dati
description: Questo argomento illustra come un amministratore di sistema o sviluppatore per la creazione di report elettronici può selezionare origini dati per un modello dati per la creazione di report elettronici.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7fccdda3ac441630836a0d33f78eb04e9cd26d4a
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092112"
---
# <a name="define-er-model-mappings-and-select-data-sources-for-them"></a><span data-ttu-id="7f6db-103">Definire i mapping di modello ER e selezionare le relative origini dati</span><span class="sxs-lookup"><span data-stu-id="7f6db-103">Define ER model mappings and select data sources for them</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7f6db-104">I passaggi seguenti descrivono come un utente con ruolo amministratore di sistema o sviluppatore per la creazione di report elettronici può selezionare origini dati per un modello dati per la creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="7f6db-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can select data sources for an Electronic reporting (ER) data model.</span></span> <span data-ttu-id="7f6db-105">Le origini dati verranno associate ai singoli componenti del modello dati selezionato in fase di progettazione e popolare i dati aziendali nel modello dati in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7f6db-105">The data sources will be bound to individual components of the selected data model at design time and populate business data to that data model at run-time.</span></span> <span data-ttu-id="7f6db-106">In questo esempio vengono selezionate le origini dati per un modello dati esistente creato per la società di esempio Litware, Inc. Per completare questi passaggi, è necessario aver completato prima i passaggi della procedura "Creare un nuovo modello dati".</span><span class="sxs-lookup"><span data-stu-id="7f6db-106">In this example, you will select data sources for an existing data model that has been created for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the "Create a new data model" procedure.</span></span>


## <a name="open-the-electronic-reporting-configurations-tree"></a><span data-ttu-id="7f6db-107">Aprire la struttura Configurazioni creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="7f6db-107">Open the Electronic Reporting configurations tree</span></span>
1. <span data-ttu-id="7f6db-108">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="7f6db-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="7f6db-109">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="7f6db-109">Click Reporting configurations.</span></span>

## <a name="insert-a-new-model-mapping"></a><span data-ttu-id="7f6db-110">Inserire un nuovo mapping di modello</span><span class="sxs-lookup"><span data-stu-id="7f6db-110">Insert a new model mapping</span></span>
1. <span data-ttu-id="7f6db-111">Nella struttura selezionare "Pagamenti (modello semplificato)".</span><span class="sxs-lookup"><span data-stu-id="7f6db-111">In the tree, select 'Payments (simplified model)'.</span></span>
2. <span data-ttu-id="7f6db-112">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="7f6db-112">Click Designer.</span></span>
3. <span data-ttu-id="7f6db-113">Fare clic su Mappa modello a origine dati.</span><span class="sxs-lookup"><span data-stu-id="7f6db-113">Click Map model to datasource.</span></span>
4. <span data-ttu-id="7f6db-114">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="7f6db-114">Click New.</span></span>
    * <span data-ttu-id="7f6db-115">Verrà creato un nuovo record che eseguirà il mapping del modello dati alle origini dati.</span><span class="sxs-lookup"><span data-stu-id="7f6db-115">This will create a new record that will map the data model to data sources.</span></span> <span data-ttu-id="7f6db-116">In questo esempio, il modello dati verrà mappato alle origini dati per il tipo di pagamento desiderato, ovvero bonifico.</span><span class="sxs-lookup"><span data-stu-id="7f6db-116">In this example, you will map the data model to data sources for the desired payment type: credit transfer.</span></span>     <span data-ttu-id="7f6db-117">È possibile progettare più di un mapping per un modello dati specifico.</span><span class="sxs-lookup"><span data-stu-id="7f6db-117">It is possible to design more than one mapping for a particular data model.</span></span> <span data-ttu-id="7f6db-118">Ad esempio, è possibile creare un mapping per i diversi tipi di pagamento, quali addebito diretto o bonifici.</span><span class="sxs-lookup"><span data-stu-id="7f6db-118">For example, you could create a mapping for the different types of payments, such as for direct debit or for credit transfers.</span></span> <span data-ttu-id="7f6db-119">In questo esempio verrà creato un mapping per i bonifici.</span><span class="sxs-lookup"><span data-stu-id="7f6db-119">In this example, you will create a mapping for credit transfers.</span></span>  
5. <span data-ttu-id="7f6db-120">Nel campo Nome digitare "Mapping bonifico".</span><span class="sxs-lookup"><span data-stu-id="7f6db-120">In the Name field, type 'CT mapping'.</span></span>
    * <span data-ttu-id="7f6db-121">Mapping bonifico</span><span class="sxs-lookup"><span data-stu-id="7f6db-121">CT mapping</span></span>  
6. <span data-ttu-id="7f6db-122">Nel campo Descrizione immettere "Mapping modello di pagamento per bonifico".</span><span class="sxs-lookup"><span data-stu-id="7f6db-122">In the Description field, type 'Payment model mapping CT'.</span></span>
    * <span data-ttu-id="7f6db-123">Mapping modello di pagamento per bonifico</span><span class="sxs-lookup"><span data-stu-id="7f6db-123">Payment model mapping CT</span></span>  
7. <span data-ttu-id="7f6db-124">Nel campo Definizione digitare 'CustomerCreditTransferInitiation'.</span><span class="sxs-lookup"><span data-stu-id="7f6db-124">In the Definition field, type 'CustomerCreditTransferInitiation'.</span></span>
    * <span data-ttu-id="7f6db-125">CustomerCreditTransferInitiation</span><span class="sxs-lookup"><span data-stu-id="7f6db-125">CustomerCreditTransferInitiation</span></span>  
8. <span data-ttu-id="7f6db-126">ResolveChanges della definizione.</span><span class="sxs-lookup"><span data-stu-id="7f6db-126">ResolveChanges the Definition.</span></span>
9. <span data-ttu-id="7f6db-127">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="7f6db-127">Click Save.</span></span>

## <a name="define-required-data-sources-for-the-current-model-mapping"></a><span data-ttu-id="7f6db-128">Definire le origini dati richieste per il mapping di modello corrente</span><span class="sxs-lookup"><span data-stu-id="7f6db-128">Define required data sources for the current model mapping</span></span>
1. <span data-ttu-id="7f6db-129">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="7f6db-129">Click Designer.</span></span>
2. <span data-ttu-id="7f6db-130">Nella struttura selezionare 'Dynamics 365 for Operations\Record di tabella'.</span><span class="sxs-lookup"><span data-stu-id="7f6db-130">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
3. <span data-ttu-id="7f6db-131">Fare clic su Aggiungi radice.</span><span class="sxs-lookup"><span data-stu-id="7f6db-131">Click Add root.</span></span>
    * <span data-ttu-id="7f6db-132">Immettere questa origine dati per accedere alle transazioni di pagamento.</span><span class="sxs-lookup"><span data-stu-id="7f6db-132">Enter this data source to access payment transactions.</span></span>  
4. <span data-ttu-id="7f6db-133">Nel campo Nome digitare "Transazioni".</span><span class="sxs-lookup"><span data-stu-id="7f6db-133">In the Name field, type 'Transactions'.</span></span>
    * <span data-ttu-id="7f6db-134">Transazioni</span><span class="sxs-lookup"><span data-stu-id="7f6db-134">Transactions</span></span>  
5. <span data-ttu-id="7f6db-135">Nel campo Etichetta immettere "Transazioni".</span><span class="sxs-lookup"><span data-stu-id="7f6db-135">In the Label field, enter 'Transactions'.</span></span>
    * <span data-ttu-id="7f6db-136">Transazioni</span><span class="sxs-lookup"><span data-stu-id="7f6db-136">Transactions</span></span>  
6. <span data-ttu-id="7f6db-137">Nel campo Guida immettere "Righe giornale di registrazione contabile".</span><span class="sxs-lookup"><span data-stu-id="7f6db-137">In the Help field, enter 'Ledger journal lines'.</span></span>
    * <span data-ttu-id="7f6db-138">Righe giornale di registrazione contabile</span><span class="sxs-lookup"><span data-stu-id="7f6db-138">Ledger journal lines</span></span>  
7. <span data-ttu-id="7f6db-139">Selezionare Sì nel campo Chiedi query.</span><span class="sxs-lookup"><span data-stu-id="7f6db-139">Select Yes in the Ask for query field.</span></span>
    * <span data-ttu-id="7f6db-140">Selezionare Sì.</span><span class="sxs-lookup"><span data-stu-id="7f6db-140">Select Yes.</span></span>  
8. <span data-ttu-id="7f6db-141">Nel campo Tabella digitare "LedgerJournalTrans".</span><span class="sxs-lookup"><span data-stu-id="7f6db-141">In the Table field, type 'LedgerJournalTrans'.</span></span>
    * <span data-ttu-id="7f6db-142">LedgerJournalTrans</span><span class="sxs-lookup"><span data-stu-id="7f6db-142">LedgerJournalTrans</span></span>  
9. <span data-ttu-id="7f6db-143">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="7f6db-143">Click OK.</span></span>
    * <span data-ttu-id="7f6db-144">Selezionare la tabella LedgerJournalTrans come origine dati per il modello dati corrente.</span><span class="sxs-lookup"><span data-stu-id="7f6db-144">Select the LedgerJournalTrans table as a data source for the current data model.</span></span>  
10. <span data-ttu-id="7f6db-145">Nella struttura selezionare "Funzioni\Campo calcolato".</span><span class="sxs-lookup"><span data-stu-id="7f6db-145">In the tree, select 'Functions\Calculated field'.</span></span>
11. <span data-ttu-id="7f6db-146">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="7f6db-146">Click Add.</span></span>
    * <span data-ttu-id="7f6db-147">Fare clic su Aggiungi per aggiungere un nuovo campo calcolato.</span><span class="sxs-lookup"><span data-stu-id="7f6db-147">Click Add to add a new calculated field.</span></span>  
12. <span data-ttu-id="7f6db-148">Nel campo Nome digitare "$EndToEndID".</span><span class="sxs-lookup"><span data-stu-id="7f6db-148">In the Name field, type '$EndToEndID'.</span></span>
    * <span data-ttu-id="7f6db-149">$EndToEndID</span><span class="sxs-lookup"><span data-stu-id="7f6db-149">$EndToEndID</span></span>  
13. <span data-ttu-id="7f6db-150">Fare clic su Modifica formula.</span><span class="sxs-lookup"><span data-stu-id="7f6db-150">Click Edit formula.</span></span>
14. <span data-ttu-id="7f6db-151">Nella struttura selezionare "Stringa\CONCATENATE".</span><span class="sxs-lookup"><span data-stu-id="7f6db-151">In the tree, select 'String\CONCATENATE'.</span></span>
15. <span data-ttu-id="7f6db-152">Fare clic su Aggiungi funzione.</span><span class="sxs-lookup"><span data-stu-id="7f6db-152">Click Add function.</span></span>
16. <span data-ttu-id="7f6db-153">Nella struttura espandere "Transazioni".</span><span class="sxs-lookup"><span data-stu-id="7f6db-153">In the tree, expand 'Transactions'.</span></span>
17. <span data-ttu-id="7f6db-154">Nella struttura espandere "Transazioni\Giustificativo".</span><span class="sxs-lookup"><span data-stu-id="7f6db-154">In the tree, select 'Transactions\Voucher'.</span></span>
18. <span data-ttu-id="7f6db-155">Fare clic su Aggiungi origine dati.</span><span class="sxs-lookup"><span data-stu-id="7f6db-155">Click Add data source.</span></span>
19. <span data-ttu-id="7f6db-156">Nel campo Formula immettere 'CONCATENATE(Transactions.Voucher, "-", '.</span><span class="sxs-lookup"><span data-stu-id="7f6db-156">In the Formula field, enter 'CONCATENATE(Transactions.Voucher, "-", '.</span></span>
    * <span data-ttu-id="7f6db-157">Digitare [ , "-", ] alla fine della formula.</span><span class="sxs-lookup"><span data-stu-id="7f6db-157">Type [ , "-", ] at the end of the formula.</span></span>  
20. <span data-ttu-id="7f6db-158">Nella struttura selezionare "Stringa\TEXT".</span><span class="sxs-lookup"><span data-stu-id="7f6db-158">In the tree, select 'String\TEXT'.</span></span>
21. <span data-ttu-id="7f6db-159">Fare clic su Aggiungi funzione.</span><span class="sxs-lookup"><span data-stu-id="7f6db-159">Click Add function.</span></span>
22. <span data-ttu-id="7f6db-160">Nella struttura selezionare "Transazioni\ID record(RecId)".</span><span class="sxs-lookup"><span data-stu-id="7f6db-160">In the tree, select 'Transactions\Record-ID(RecId)'.</span></span>
23. <span data-ttu-id="7f6db-161">Fare clic su Aggiungi origine dati.</span><span class="sxs-lookup"><span data-stu-id="7f6db-161">Click Add data source.</span></span>
24. <span data-ttu-id="7f6db-162">Nel campo Formula immettere 'CONCATENATE(Transactions.Voucher, "-", TEXT(Transactions.RecId))'.</span><span class="sxs-lookup"><span data-stu-id="7f6db-162">In the Formula field, enter 'CONCATENATE(Transactions.Voucher, "-", TEXT(Transactions.RecId))'.</span></span>
    * <span data-ttu-id="7f6db-163">Digitare [))] alla fine della formula.</span><span class="sxs-lookup"><span data-stu-id="7f6db-163">Type [))] at the end of the formula.</span></span>  
25. <span data-ttu-id="7f6db-164">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="7f6db-164">Click Save.</span></span>
    * <span data-ttu-id="7f6db-165">Assicurarsi che non sia stato rilevato alcun errore per la formula creata.</span><span class="sxs-lookup"><span data-stu-id="7f6db-165">Make sure that no errors have been discovered for the created formula.</span></span> <span data-ttu-id="7f6db-166">Vedere la scheda ERRORI sotto il controllo dell'editor della formula.</span><span class="sxs-lookup"><span data-stu-id="7f6db-166">See the ERRORS tab below the formula editor control.</span></span>  
26. <span data-ttu-id="7f6db-167">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="7f6db-167">Close the page.</span></span>
27. <span data-ttu-id="7f6db-168">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="7f6db-168">Click OK.</span></span>
    * <span data-ttu-id="7f6db-169">Aggiungere il campo calcolato all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="7f6db-169">Add the calculated field to this data source.</span></span>  
28. <span data-ttu-id="7f6db-170">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="7f6db-170">Click Add.</span></span>
    * <span data-ttu-id="7f6db-171">Fare clic su Aggiungi per aggiungere un nuovo campo calcolato.</span><span class="sxs-lookup"><span data-stu-id="7f6db-171">Click Add to add a new calculated field.</span></span>  
29. <span data-ttu-id="7f6db-172">Nel campo Nome digitare "$Amount".</span><span class="sxs-lookup"><span data-stu-id="7f6db-172">In the Name field, type '$Amount'.</span></span>
    * <span data-ttu-id="7f6db-173">$Amount</span><span class="sxs-lookup"><span data-stu-id="7f6db-173">$Amount</span></span>  
30. <span data-ttu-id="7f6db-174">Fare clic su Modifica formula.</span><span class="sxs-lookup"><span data-stu-id="7f6db-174">Click Edit formula.</span></span>
31. <span data-ttu-id="7f6db-175">Nella struttura espandere "Transazioni".</span><span class="sxs-lookup"><span data-stu-id="7f6db-175">In the tree, expand 'Transactions'.</span></span>
32. <span data-ttu-id="7f6db-176">Nella struttura selezionare "Transazioni\Dare(AmountCurDebit)".</span><span class="sxs-lookup"><span data-stu-id="7f6db-176">In the tree, select 'Transactions\Debit(AmountCurDebit)'.</span></span>
33. <span data-ttu-id="7f6db-177">Fare clic su Aggiungi origine dati.</span><span class="sxs-lookup"><span data-stu-id="7f6db-177">Click Add data source.</span></span>
34. <span data-ttu-id="7f6db-178">Nel campo Formula immettere 'Transactions.AmountCurDebit - '.</span><span class="sxs-lookup"><span data-stu-id="7f6db-178">In the Formula field, enter 'Transactions.AmountCurDebit - '.</span></span>
    * <span data-ttu-id="7f6db-179">Digitare [ - ] alla fine della formula.</span><span class="sxs-lookup"><span data-stu-id="7f6db-179">Type [ - ] at the end of the formula.</span></span>  
35. <span data-ttu-id="7f6db-180">Nella struttura selezionare "Transazioni\Avere(AmountCurCredit)".</span><span class="sxs-lookup"><span data-stu-id="7f6db-180">In the tree, select 'Transactions\Credit(AmountCurCredit)'.</span></span>
36. <span data-ttu-id="7f6db-181">Fare clic su Aggiungi origine dati.</span><span class="sxs-lookup"><span data-stu-id="7f6db-181">Click Add data source.</span></span>
37. <span data-ttu-id="7f6db-182">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="7f6db-182">Click Save.</span></span>
38. <span data-ttu-id="7f6db-183">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="7f6db-183">Close the page.</span></span>
39. <span data-ttu-id="7f6db-184">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="7f6db-184">Click OK.</span></span>
    * <span data-ttu-id="7f6db-185">Il campo calcolato $Amount verrà aggiunto all'origine dati selezionata per il modello dati corrente.</span><span class="sxs-lookup"><span data-stu-id="7f6db-185">This will add the $Amount calculated field to the selected data source for the current data model.</span></span>  
40. <span data-ttu-id="7f6db-186">Nella struttura selezionare "Transazioni\$Amount".</span><span class="sxs-lookup"><span data-stu-id="7f6db-186">In the tree, select 'Transactions\$Amount'.</span></span>
41. <span data-ttu-id="7f6db-187">Nella struttura espandere "Transazioni".</span><span class="sxs-lookup"><span data-stu-id="7f6db-187">In the tree, expand 'Transactions'.</span></span>
42. <span data-ttu-id="7f6db-188">Nella struttura espandere o comprimere 'Transazioni\$Amount'.</span><span class="sxs-lookup"><span data-stu-id="7f6db-188">In the tree, expand or collapse 'Transactions\$Amount'.</span></span>
43. <span data-ttu-id="7f6db-189">Nella struttura espandere o comprimere 'Transazioni'.</span><span class="sxs-lookup"><span data-stu-id="7f6db-189">In the tree, expand or collapse 'Transactions'.</span></span>
44. <span data-ttu-id="7f6db-190">Nella struttura selezionare 'Dynamics 365 for Operations\Record di tabella'.</span><span class="sxs-lookup"><span data-stu-id="7f6db-190">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
45. <span data-ttu-id="7f6db-191">Fare clic su Aggiungi radice.</span><span class="sxs-lookup"><span data-stu-id="7f6db-191">Click Add root.</span></span>
    * <span data-ttu-id="7f6db-192">Immettere l'origine dati per accedere ai dettagli del conto bancario della società.</span><span class="sxs-lookup"><span data-stu-id="7f6db-192">Enter this data source to access the company's bank account details.</span></span>  
46. <span data-ttu-id="7f6db-193">Nel campo Nome digitare "BankAccount".</span><span class="sxs-lookup"><span data-stu-id="7f6db-193">In the Name field, type 'BankAccount'.</span></span>
    * <span data-ttu-id="7f6db-194">BankAccount</span><span class="sxs-lookup"><span data-stu-id="7f6db-194">BankAccount</span></span>  
47. <span data-ttu-id="7f6db-195">Nel campo Etichetta immettere "Conto bancario".</span><span class="sxs-lookup"><span data-stu-id="7f6db-195">In the Label field, enter 'Bank Account'.</span></span>
    * <span data-ttu-id="7f6db-196">Conto bancario</span><span class="sxs-lookup"><span data-stu-id="7f6db-196">Bank Account</span></span>  
48. <span data-ttu-id="7f6db-197">Nel campo Guida immettere "Conto bancario".</span><span class="sxs-lookup"><span data-stu-id="7f6db-197">In the Help field, enter 'Bank Account'.</span></span>
    * <span data-ttu-id="7f6db-198">Conto bancario</span><span class="sxs-lookup"><span data-stu-id="7f6db-198">Bank Account</span></span>  
49. <span data-ttu-id="7f6db-199">Selezionare Sì nel campo Chiedi query.</span><span class="sxs-lookup"><span data-stu-id="7f6db-199">Select Yes in the Ask for query field.</span></span>
    * <span data-ttu-id="7f6db-200">Selezionare Sì.</span><span class="sxs-lookup"><span data-stu-id="7f6db-200">Select Yes.</span></span>  
50. <span data-ttu-id="7f6db-201">Nel campo Tabella digitare "BankAccountTable".</span><span class="sxs-lookup"><span data-stu-id="7f6db-201">In the Table field, type 'BankAccountTable'.</span></span>
    * <span data-ttu-id="7f6db-202">BankAccountTable</span><span class="sxs-lookup"><span data-stu-id="7f6db-202">BankAccountTable</span></span>  
51. <span data-ttu-id="7f6db-203">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="7f6db-203">Click OK.</span></span>
    * <span data-ttu-id="7f6db-204">Selezionare la tabella BankAccountTable come origine dati per il modello dati corrente.</span><span class="sxs-lookup"><span data-stu-id="7f6db-204">Select the BankAccountTable table as a data source for the current data model.</span></span>  
52. <span data-ttu-id="7f6db-205">Fare clic su Aggiungi radice.</span><span class="sxs-lookup"><span data-stu-id="7f6db-205">Click Add root.</span></span>
    * <span data-ttu-id="7f6db-206">Immettere l'origine dati per accedere ai requisiti della società.</span><span class="sxs-lookup"><span data-stu-id="7f6db-206">Enter this data source to access the company's requisites.</span></span>  
53. <span data-ttu-id="7f6db-207">Nel campo Nome digitare "Società".</span><span class="sxs-lookup"><span data-stu-id="7f6db-207">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="7f6db-208">Società</span><span class="sxs-lookup"><span data-stu-id="7f6db-208">Company</span></span>  
54. <span data-ttu-id="7f6db-209">Nel campo Etichetta digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="7f6db-209">In the Label field, type a value.</span></span>
    * <span data-ttu-id="7f6db-210">Informazioni società</span><span class="sxs-lookup"><span data-stu-id="7f6db-210">Company information</span></span>  
55. <span data-ttu-id="7f6db-211">Nel campo Guida immettere "Informazioni società".</span><span class="sxs-lookup"><span data-stu-id="7f6db-211">In the Help field, enter 'Company information'.</span></span>
    * <span data-ttu-id="7f6db-212">Informazioni società</span><span class="sxs-lookup"><span data-stu-id="7f6db-212">Company information</span></span>  
56. <span data-ttu-id="7f6db-213">Selezionare Sì nel campo Chiedi query.</span><span class="sxs-lookup"><span data-stu-id="7f6db-213">Select Yes in the Ask for query field.</span></span>
    * <span data-ttu-id="7f6db-214">Selezionare Sì.</span><span class="sxs-lookup"><span data-stu-id="7f6db-214">Select Yes.</span></span>  
57. <span data-ttu-id="7f6db-215">Nel campo Tabella digitare "CompanyInfo".</span><span class="sxs-lookup"><span data-stu-id="7f6db-215">In the Table field, type 'CompanyInfo'.</span></span>
    * <span data-ttu-id="7f6db-216">CompanyInfo</span><span class="sxs-lookup"><span data-stu-id="7f6db-216">CompanyInfo</span></span>  
58. <span data-ttu-id="7f6db-217">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="7f6db-217">Click OK.</span></span>
    * <span data-ttu-id="7f6db-218">Selezionare la tabella CompanyInfo come origine dati per il modello dati corrente.</span><span class="sxs-lookup"><span data-stu-id="7f6db-218">Select the CompanyInfo table as a data source for the current data model.</span></span>  
59. <span data-ttu-id="7f6db-219">Nella struttura selezionare "Funzioni\Campo calcolato".</span><span class="sxs-lookup"><span data-stu-id="7f6db-219">In the tree, select 'Functions\Calculated field'.</span></span>
60. <span data-ttu-id="7f6db-220">Fare clic su Aggiungi radice.</span><span class="sxs-lookup"><span data-stu-id="7f6db-220">Click Add root.</span></span>
    * <span data-ttu-id="7f6db-221">Inserire un campo calcolato come nuova origine dati.</span><span class="sxs-lookup"><span data-stu-id="7f6db-221">Insert a calculated field as a new data source.</span></span>  
61. <span data-ttu-id="7f6db-222">Nel campo Nome digitare "ProcessingDateTime".</span><span class="sxs-lookup"><span data-stu-id="7f6db-222">In the Name field, type 'ProcessingDateTime'.</span></span>
    * <span data-ttu-id="7f6db-223">ProcessingDateTime</span><span class="sxs-lookup"><span data-stu-id="7f6db-223">ProcessingDateTime</span></span>  
62. <span data-ttu-id="7f6db-224">Nel campo Etichetta immettere "Data e ora di elaborazione".</span><span class="sxs-lookup"><span data-stu-id="7f6db-224">In the Label field, enter 'Processing date & time'.</span></span>
    * <span data-ttu-id="7f6db-225">Data e ora di elaborazione</span><span class="sxs-lookup"><span data-stu-id="7f6db-225">Processing date & time</span></span>  
63. <span data-ttu-id="7f6db-226">Fare clic su Modifica formula.</span><span class="sxs-lookup"><span data-stu-id="7f6db-226">Click Edit formula.</span></span>
64. <span data-ttu-id="7f6db-227">Nella struttura selezionare 'Data/ora\SESSIONNOW'.</span><span class="sxs-lookup"><span data-stu-id="7f6db-227">In the tree, select 'Date/time\SESSIONNOW'.</span></span>
65. <span data-ttu-id="7f6db-228">Fare clic su Aggiungi funzione.</span><span class="sxs-lookup"><span data-stu-id="7f6db-228">Click Add function.</span></span>
66. <span data-ttu-id="7f6db-229">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="7f6db-229">Click Save.</span></span>
67. <span data-ttu-id="7f6db-230">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="7f6db-230">Close the page.</span></span>
68. <span data-ttu-id="7f6db-231">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="7f6db-231">Click OK.</span></span>
    * <span data-ttu-id="7f6db-232">Aggiungere il campo calcolato ProcessingDateTime come origine dati per il modello dati corrente.</span><span class="sxs-lookup"><span data-stu-id="7f6db-232">Add the ProcessingDateTime calculated field as a data source for the current data model.</span></span>  
69. <span data-ttu-id="7f6db-233">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="7f6db-233">Click Save.</span></span>
70. <span data-ttu-id="7f6db-234">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="7f6db-234">Close the page.</span></span>
71. <span data-ttu-id="7f6db-235">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="7f6db-235">Close the page.</span></span>
72. <span data-ttu-id="7f6db-236">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="7f6db-236">Close the page.</span></span>

