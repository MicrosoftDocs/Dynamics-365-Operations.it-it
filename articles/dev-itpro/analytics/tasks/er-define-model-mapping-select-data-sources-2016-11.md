---
title: Definire i mapping di modello ER e selezionare le relative origini dati
description: I passaggi seguenti descrivono come un utente con ruolo amministratore di sistema o sviluppatore per la creazione di report elettronici può selezionare origini dati per un modello dati per la creazione di report elettronici.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b5f2f2c699514d723f42f5d1fb25724f46dfc4f4
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "348873"
---
# <a name="define-er-model-mappings-and-select-data-sources-for-them"></a><span data-ttu-id="b027d-103">Definire i mapping di modello ER e selezionare le relative origini dati</span><span class="sxs-lookup"><span data-stu-id="b027d-103">Define ER model mappings and select data sources for them</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b027d-104">I passaggi seguenti descrivono come un utente con ruolo amministratore di sistema o sviluppatore per la creazione di report elettronici può selezionare origini dati per un modello dati per la creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="b027d-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can select data sources for an Electronic reporting (ER) data model.</span></span> <span data-ttu-id="b027d-105">Le origini dati verranno associate ai singoli componenti del modello dati selezionato in fase di progettazione e popolare i dati aziendali nel modello dati in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b027d-105">The data sources will be bound to individual components of the selected data model at design time and populate business data to that data model at run-time.</span></span> <span data-ttu-id="b027d-106">In questo esempio vengono selezionate le origini dati per un modello dati esistente creato per la società di esempio Litware, Inc. Per completare questi passaggi, è necessario aver completato prima i passaggi della procedura "Creare un nuovo modello dati".</span><span class="sxs-lookup"><span data-stu-id="b027d-106">In this example, you will select data sources for an existing data model that has been created for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the “Create a new data model” procedure.</span></span>


## <a name="open-the-electronic-reporting-configurations-tree"></a><span data-ttu-id="b027d-107">Aprire la struttura Configurazioni creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="b027d-107">Open the Electronic Reporting configurations tree</span></span>
1. <span data-ttu-id="b027d-108">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="b027d-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="b027d-109">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="b027d-109">Click Reporting configurations.</span></span>

## <a name="insert-a-new-model-mapping"></a><span data-ttu-id="b027d-110">Inserire un nuovo mapping di modello</span><span class="sxs-lookup"><span data-stu-id="b027d-110">Insert a new model mapping</span></span>
1. <span data-ttu-id="b027d-111">Nella struttura selezionare "Pagamenti (modello semplificato)".</span><span class="sxs-lookup"><span data-stu-id="b027d-111">In the tree, select 'Payments (simplified model)'.</span></span>
2. <span data-ttu-id="b027d-112">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="b027d-112">Click Designer.</span></span>
3. <span data-ttu-id="b027d-113">Fare clic su Mappa modello a origine dati.</span><span class="sxs-lookup"><span data-stu-id="b027d-113">Click Map model to datasource.</span></span>
4. <span data-ttu-id="b027d-114">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="b027d-114">Click New.</span></span>
    * <span data-ttu-id="b027d-115">Verrà creato un nuovo record che eseguirà il mapping del modello dati alle origini dati.</span><span class="sxs-lookup"><span data-stu-id="b027d-115">This will create a new record that will map the data model to data sources.</span></span> <span data-ttu-id="b027d-116">In questo esempio, il modello dati verrà mappato alle origini dati per il tipo di pagamento desiderato, ovvero bonifico.</span><span class="sxs-lookup"><span data-stu-id="b027d-116">In this example, you will map the data model to data sources for the desired payment type: credit transfer.</span></span>     <span data-ttu-id="b027d-117">È possibile progettare più di un mapping per un modello dati specifico.</span><span class="sxs-lookup"><span data-stu-id="b027d-117">It is possible to design more than one mapping for a particular data model.</span></span> <span data-ttu-id="b027d-118">Ad esempio, è possibile creare un mapping per i diversi tipi di pagamento, quali addebito diretto o bonifici.</span><span class="sxs-lookup"><span data-stu-id="b027d-118">For example, you could create a mapping for the different types of payments, such as for direct debit or for credit transfers.</span></span> <span data-ttu-id="b027d-119">In questo esempio verrà creato un mapping per i bonifici.</span><span class="sxs-lookup"><span data-stu-id="b027d-119">In this example, you will create a mapping for credit transfers.</span></span>  
5. <span data-ttu-id="b027d-120">Nel campo Nome digitare "Mapping bonifico".</span><span class="sxs-lookup"><span data-stu-id="b027d-120">In the Name field, type 'CT mapping'.</span></span>
    * <span data-ttu-id="b027d-121">Mapping bonifico</span><span class="sxs-lookup"><span data-stu-id="b027d-121">CT mapping</span></span>  
6. <span data-ttu-id="b027d-122">Nel campo Descrizione immettere "Mapping modello di pagamento per bonifico".</span><span class="sxs-lookup"><span data-stu-id="b027d-122">In the Description field, type 'Payment model mapping CT'.</span></span>
    * <span data-ttu-id="b027d-123">Mapping modello di pagamento per bonifico</span><span class="sxs-lookup"><span data-stu-id="b027d-123">Payment model mapping CT</span></span>  
7. <span data-ttu-id="b027d-124">Nel campo Definizione digitare 'CustomerCreditTransferInitiation'.</span><span class="sxs-lookup"><span data-stu-id="b027d-124">In the Definition field, type 'CustomerCreditTransferInitiation'.</span></span>
    * <span data-ttu-id="b027d-125">CustomerCreditTransferInitiation</span><span class="sxs-lookup"><span data-stu-id="b027d-125">CustomerCreditTransferInitiation</span></span>  
8. <span data-ttu-id="b027d-126">ResolveChanges della definizione.</span><span class="sxs-lookup"><span data-stu-id="b027d-126">ResolveChanges the Definition.</span></span>
9. <span data-ttu-id="b027d-127">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="b027d-127">Click Save.</span></span>

## <a name="define-required-data-sources-for-the-current-model-mapping"></a><span data-ttu-id="b027d-128">Definire le origini dati richieste per il mapping di modello corrente</span><span class="sxs-lookup"><span data-stu-id="b027d-128">Define required data sources for the current model mapping</span></span>
1. <span data-ttu-id="b027d-129">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="b027d-129">Click Designer.</span></span>
2. <span data-ttu-id="b027d-130">Nella struttura selezionare 'Dynamics 365 for Operations\Record di tabella'.</span><span class="sxs-lookup"><span data-stu-id="b027d-130">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
3. <span data-ttu-id="b027d-131">Fare clic su Aggiungi radice.</span><span class="sxs-lookup"><span data-stu-id="b027d-131">Click Add root.</span></span>
    * <span data-ttu-id="b027d-132">Immettere questa origine dati per accedere alle transazioni di pagamento.</span><span class="sxs-lookup"><span data-stu-id="b027d-132">Enter this data source to access payment transactions.</span></span>  
4. <span data-ttu-id="b027d-133">Nel campo Nome digitare "Transazioni".</span><span class="sxs-lookup"><span data-stu-id="b027d-133">In the Name field, type 'Transactions'.</span></span>
    * <span data-ttu-id="b027d-134">Transazioni</span><span class="sxs-lookup"><span data-stu-id="b027d-134">Transactions</span></span>  
5. <span data-ttu-id="b027d-135">Nel campo Etichetta immettere "Transazioni".</span><span class="sxs-lookup"><span data-stu-id="b027d-135">In the Label field, enter 'Transactions'.</span></span>
    * <span data-ttu-id="b027d-136">Transazioni</span><span class="sxs-lookup"><span data-stu-id="b027d-136">Transactions</span></span>  
6. <span data-ttu-id="b027d-137">Nel campo Guida immettere "Righe giornale di registrazione contabile".</span><span class="sxs-lookup"><span data-stu-id="b027d-137">In the Help field, enter 'Ledger journal lines'.</span></span>
    * <span data-ttu-id="b027d-138">Righe giornale di registrazione contabile</span><span class="sxs-lookup"><span data-stu-id="b027d-138">Ledger journal lines</span></span>  
7. <span data-ttu-id="b027d-139">Selezionare Sì nel campo Chiedi query.</span><span class="sxs-lookup"><span data-stu-id="b027d-139">Select Yes in the Ask for query field.</span></span>
    * <span data-ttu-id="b027d-140">Selezionare Sì.</span><span class="sxs-lookup"><span data-stu-id="b027d-140">Select Yes.</span></span>  
8. <span data-ttu-id="b027d-141">Nel campo Tabella digitare "LedgerJournalTrans".</span><span class="sxs-lookup"><span data-stu-id="b027d-141">In the Table field, type 'LedgerJournalTrans'.</span></span>
    * <span data-ttu-id="b027d-142">LedgerJournalTrans</span><span class="sxs-lookup"><span data-stu-id="b027d-142">LedgerJournalTrans</span></span>  
9. <span data-ttu-id="b027d-143">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="b027d-143">Click OK.</span></span>
    * <span data-ttu-id="b027d-144">Selezionare la tabella LedgerJournalTrans come origine dati per il modello dati corrente.</span><span class="sxs-lookup"><span data-stu-id="b027d-144">Select the LedgerJournalTrans table as a data source for the current data model.</span></span>  
10. <span data-ttu-id="b027d-145">Nella struttura selezionare "Funzioni\Campo calcolato".</span><span class="sxs-lookup"><span data-stu-id="b027d-145">In the tree, select 'Functions\Calculated field'.</span></span>
11. <span data-ttu-id="b027d-146">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="b027d-146">Click Add.</span></span>
    * <span data-ttu-id="b027d-147">Fare clic su Aggiungi per aggiungere un nuovo campo calcolato.</span><span class="sxs-lookup"><span data-stu-id="b027d-147">Click Add to add a new calculated field.</span></span>  
12. <span data-ttu-id="b027d-148">Nel campo Nome digitare "$EndToEndID".</span><span class="sxs-lookup"><span data-stu-id="b027d-148">In the Name field, type '$EndToEndID'.</span></span>
    * <span data-ttu-id="b027d-149">$EndToEndID</span><span class="sxs-lookup"><span data-stu-id="b027d-149">$EndToEndID</span></span>  
13. <span data-ttu-id="b027d-150">Fare clic su Modifica formula.</span><span class="sxs-lookup"><span data-stu-id="b027d-150">Click Edit formula.</span></span>
14. <span data-ttu-id="b027d-151">Nella struttura selezionare "Stringa\CONCATENATE".</span><span class="sxs-lookup"><span data-stu-id="b027d-151">In the tree, select 'String\CONCATENATE'.</span></span>
15. <span data-ttu-id="b027d-152">Fare clic su Aggiungi funzione.</span><span class="sxs-lookup"><span data-stu-id="b027d-152">Click Add function.</span></span>
16. <span data-ttu-id="b027d-153">Nella struttura espandere "Transazioni".</span><span class="sxs-lookup"><span data-stu-id="b027d-153">In the tree, expand 'Transactions'.</span></span>
17. <span data-ttu-id="b027d-154">Nella struttura espandere "Transazioni\Giustificativo".</span><span class="sxs-lookup"><span data-stu-id="b027d-154">In the tree, select 'Transactions\Voucher'.</span></span>
18. <span data-ttu-id="b027d-155">Fare clic su Aggiungi origine dati.</span><span class="sxs-lookup"><span data-stu-id="b027d-155">Click Add data source.</span></span>
19. <span data-ttu-id="b027d-156">Nel campo Formula immettere 'CONCATENATE(Transactions.Voucher, "-", '.</span><span class="sxs-lookup"><span data-stu-id="b027d-156">In the Formula field, enter 'CONCATENATE(Transactions.Voucher, "-", '.</span></span>
    * <span data-ttu-id="b027d-157">Digitare [ , “-“, ] alla fine della formula.</span><span class="sxs-lookup"><span data-stu-id="b027d-157">Type [ , “-“, ] at the end of the formula.</span></span>  
20. <span data-ttu-id="b027d-158">Nella struttura selezionare "Stringa\TEXT".</span><span class="sxs-lookup"><span data-stu-id="b027d-158">In the tree, select 'String\TEXT'.</span></span>
21. <span data-ttu-id="b027d-159">Fare clic su Aggiungi funzione.</span><span class="sxs-lookup"><span data-stu-id="b027d-159">Click Add function.</span></span>
22. <span data-ttu-id="b027d-160">Nella struttura selezionare "Transazioni\ID record(RecId)".</span><span class="sxs-lookup"><span data-stu-id="b027d-160">In the tree, select 'Transactions\Record-ID(RecId)'.</span></span>
23. <span data-ttu-id="b027d-161">Fare clic su Aggiungi origine dati.</span><span class="sxs-lookup"><span data-stu-id="b027d-161">Click Add data source.</span></span>
24. <span data-ttu-id="b027d-162">Nel campo Formula immettere 'CONCATENATE(Transactions.Voucher, "-", TEXT(Transactions.RecId))'.</span><span class="sxs-lookup"><span data-stu-id="b027d-162">In the Formula field, enter 'CONCATENATE(Transactions.Voucher, "-", TEXT(Transactions.RecId))'.</span></span>
    * <span data-ttu-id="b027d-163">Digitare [))] alla fine della formula.</span><span class="sxs-lookup"><span data-stu-id="b027d-163">Type [))] at the end of the formula.</span></span>  
25. <span data-ttu-id="b027d-164">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="b027d-164">Click Save.</span></span>
    * <span data-ttu-id="b027d-165">Assicurarsi che non sia stato rilevato alcun errore per la formula creata.</span><span class="sxs-lookup"><span data-stu-id="b027d-165">Make sure that no errors have been discovered for the created formula.</span></span> <span data-ttu-id="b027d-166">Vedere la scheda ERRORI sotto il controllo dell'editor della formula.</span><span class="sxs-lookup"><span data-stu-id="b027d-166">See the ERRORS tab below the formula editor control.</span></span>  
26. <span data-ttu-id="b027d-167">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="b027d-167">Close the page.</span></span>
27. <span data-ttu-id="b027d-168">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="b027d-168">Click OK.</span></span>
    * <span data-ttu-id="b027d-169">Aggiungere il campo calcolato all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="b027d-169">Add the calculated field to this data source.</span></span>  
28. <span data-ttu-id="b027d-170">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="b027d-170">Click Add.</span></span>
    * <span data-ttu-id="b027d-171">Fare clic su Aggiungi per aggiungere un nuovo campo calcolato.</span><span class="sxs-lookup"><span data-stu-id="b027d-171">Click Add to add a new calculated field.</span></span>  
29. <span data-ttu-id="b027d-172">Nel campo Nome digitare "$Amount".</span><span class="sxs-lookup"><span data-stu-id="b027d-172">In the Name field, type '$Amount'.</span></span>
    * <span data-ttu-id="b027d-173">$Amount</span><span class="sxs-lookup"><span data-stu-id="b027d-173">$Amount</span></span>  
30. <span data-ttu-id="b027d-174">Fare clic su Modifica formula.</span><span class="sxs-lookup"><span data-stu-id="b027d-174">Click Edit formula.</span></span>
31. <span data-ttu-id="b027d-175">Nella struttura espandere "Transazioni".</span><span class="sxs-lookup"><span data-stu-id="b027d-175">In the tree, expand 'Transactions'.</span></span>
32. <span data-ttu-id="b027d-176">Nella struttura selezionare "Transazioni\Dare(AmountCurDebit)".</span><span class="sxs-lookup"><span data-stu-id="b027d-176">In the tree, select 'Transactions\Debit(AmountCurDebit)'.</span></span>
33. <span data-ttu-id="b027d-177">Fare clic su Aggiungi origine dati.</span><span class="sxs-lookup"><span data-stu-id="b027d-177">Click Add data source.</span></span>
34. <span data-ttu-id="b027d-178">Nel campo Formula immettere 'Transactions.AmountCurDebit - '.</span><span class="sxs-lookup"><span data-stu-id="b027d-178">In the Formula field, enter 'Transactions.AmountCurDebit - '.</span></span>
    * <span data-ttu-id="b027d-179">Digitare [ - ] alla fine della formula.</span><span class="sxs-lookup"><span data-stu-id="b027d-179">Type [ - ] at the end of the formula.</span></span>  
35. <span data-ttu-id="b027d-180">Nella struttura selezionare "Transazioni\Avere(AmountCurCredit)".</span><span class="sxs-lookup"><span data-stu-id="b027d-180">In the tree, select 'Transactions\Credit(AmountCurCredit)'.</span></span>
36. <span data-ttu-id="b027d-181">Fare clic su Aggiungi origine dati.</span><span class="sxs-lookup"><span data-stu-id="b027d-181">Click Add data source.</span></span>
37. <span data-ttu-id="b027d-182">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="b027d-182">Click Save.</span></span>
38. <span data-ttu-id="b027d-183">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="b027d-183">Close the page.</span></span>
39. <span data-ttu-id="b027d-184">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="b027d-184">Click OK.</span></span>
    * <span data-ttu-id="b027d-185">Il campo calcolato $Amount verrà aggiunto all'origine dati selezionata per il modello dati corrente.</span><span class="sxs-lookup"><span data-stu-id="b027d-185">This will add the $Amount calculated field to the selected data source for the current data model.</span></span>  
40. <span data-ttu-id="b027d-186">Nella struttura selezionare "Transazioni\$Amount".</span><span class="sxs-lookup"><span data-stu-id="b027d-186">In the tree, select 'Transactions\$Amount'.</span></span>
41. <span data-ttu-id="b027d-187">Nella struttura espandere "Transazioni".</span><span class="sxs-lookup"><span data-stu-id="b027d-187">In the tree, expand 'Transactions'.</span></span>
42. <span data-ttu-id="b027d-188">Nella struttura espandere o comprimere 'Transazioni\$Amount'.</span><span class="sxs-lookup"><span data-stu-id="b027d-188">In the tree, expand or collapse 'Transactions\$Amount'.</span></span>
43. <span data-ttu-id="b027d-189">Nella struttura espandere o comprimere 'Transazioni'.</span><span class="sxs-lookup"><span data-stu-id="b027d-189">In the tree, expand or collapse 'Transactions'.</span></span>
44. <span data-ttu-id="b027d-190">Nella struttura selezionare 'Dynamics 365 for Operations\Record di tabella'.</span><span class="sxs-lookup"><span data-stu-id="b027d-190">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
45. <span data-ttu-id="b027d-191">Fare clic su Aggiungi radice.</span><span class="sxs-lookup"><span data-stu-id="b027d-191">Click Add root.</span></span>
    * <span data-ttu-id="b027d-192">Immettere l'origine dati per accedere ai dettagli del conto bancario della società.</span><span class="sxs-lookup"><span data-stu-id="b027d-192">Enter this data source to access the company’s bank account details.</span></span>  
46. <span data-ttu-id="b027d-193">Nel campo Nome digitare "BankAccount".</span><span class="sxs-lookup"><span data-stu-id="b027d-193">In the Name field, type 'BankAccount'.</span></span>
    * <span data-ttu-id="b027d-194">BankAccount</span><span class="sxs-lookup"><span data-stu-id="b027d-194">BankAccount</span></span>  
47. <span data-ttu-id="b027d-195">Nel campo Etichetta immettere "Conto bancario".</span><span class="sxs-lookup"><span data-stu-id="b027d-195">In the Label field, enter 'Bank Account'.</span></span>
    * <span data-ttu-id="b027d-196">Conto bancario</span><span class="sxs-lookup"><span data-stu-id="b027d-196">Bank Account</span></span>  
48. <span data-ttu-id="b027d-197">Nel campo Guida immettere "Conto bancario".</span><span class="sxs-lookup"><span data-stu-id="b027d-197">In the Help field, enter 'Bank Account'.</span></span>
    * <span data-ttu-id="b027d-198">Conto bancario</span><span class="sxs-lookup"><span data-stu-id="b027d-198">Bank Account</span></span>  
49. <span data-ttu-id="b027d-199">Selezionare Sì nel campo Chiedi query.</span><span class="sxs-lookup"><span data-stu-id="b027d-199">Select Yes in the Ask for query field.</span></span>
    * <span data-ttu-id="b027d-200">Selezionare Sì.</span><span class="sxs-lookup"><span data-stu-id="b027d-200">Select Yes.</span></span>  
50. <span data-ttu-id="b027d-201">Nel campo Tabella digitare "BankAccountTable".</span><span class="sxs-lookup"><span data-stu-id="b027d-201">In the Table field, type 'BankAccountTable'.</span></span>
    * <span data-ttu-id="b027d-202">BankAccountTable</span><span class="sxs-lookup"><span data-stu-id="b027d-202">BankAccountTable</span></span>  
51. <span data-ttu-id="b027d-203">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="b027d-203">Click OK.</span></span>
    * <span data-ttu-id="b027d-204">Selezionare la tabella BankAccountTable come origine dati per il modello dati corrente.</span><span class="sxs-lookup"><span data-stu-id="b027d-204">Select the BankAccountTable table as a data source for the current data model.</span></span>  
52. <span data-ttu-id="b027d-205">Fare clic su Aggiungi radice.</span><span class="sxs-lookup"><span data-stu-id="b027d-205">Click Add root.</span></span>
    * <span data-ttu-id="b027d-206">Immettere l'origine dati per accedere ai requisiti della società.</span><span class="sxs-lookup"><span data-stu-id="b027d-206">Enter this data source to access the company’s requisites.</span></span>  
53. <span data-ttu-id="b027d-207">Nel campo Nome digitare "Società".</span><span class="sxs-lookup"><span data-stu-id="b027d-207">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="b027d-208">Società</span><span class="sxs-lookup"><span data-stu-id="b027d-208">Company</span></span>  
54. <span data-ttu-id="b027d-209">Nel campo Etichetta digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="b027d-209">In the Label field, type a value.</span></span>
    * <span data-ttu-id="b027d-210">Informazioni società</span><span class="sxs-lookup"><span data-stu-id="b027d-210">Company information</span></span>  
55. <span data-ttu-id="b027d-211">Nel campo Guida immettere "Informazioni società".</span><span class="sxs-lookup"><span data-stu-id="b027d-211">In the Help field, enter 'Company information'.</span></span>
    * <span data-ttu-id="b027d-212">Informazioni società</span><span class="sxs-lookup"><span data-stu-id="b027d-212">Company information</span></span>  
56. <span data-ttu-id="b027d-213">Selezionare Sì nel campo Chiedi query.</span><span class="sxs-lookup"><span data-stu-id="b027d-213">Select Yes in the Ask for query field.</span></span>
    * <span data-ttu-id="b027d-214">Selezionare Sì.</span><span class="sxs-lookup"><span data-stu-id="b027d-214">Select Yes.</span></span>  
57. <span data-ttu-id="b027d-215">Nel campo Tabella digitare "CompanyInfo".</span><span class="sxs-lookup"><span data-stu-id="b027d-215">In the Table field, type 'CompanyInfo'.</span></span>
    * <span data-ttu-id="b027d-216">CompanyInfo</span><span class="sxs-lookup"><span data-stu-id="b027d-216">CompanyInfo</span></span>  
58. <span data-ttu-id="b027d-217">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="b027d-217">Click OK.</span></span>
    * <span data-ttu-id="b027d-218">Selezionare la tabella CompanyInfo come origine dati per il modello dati corrente.</span><span class="sxs-lookup"><span data-stu-id="b027d-218">Select the CompanyInfo table as a data source for the current data model.</span></span>  
59. <span data-ttu-id="b027d-219">Nella struttura selezionare "Funzioni\Campo calcolato".</span><span class="sxs-lookup"><span data-stu-id="b027d-219">In the tree, select 'Functions\Calculated field'.</span></span>
60. <span data-ttu-id="b027d-220">Fare clic su Aggiungi radice.</span><span class="sxs-lookup"><span data-stu-id="b027d-220">Click Add root.</span></span>
    * <span data-ttu-id="b027d-221">Inserire un campo calcolato come nuova origine dati.</span><span class="sxs-lookup"><span data-stu-id="b027d-221">Insert a calculated field as a new data source.</span></span>  
61. <span data-ttu-id="b027d-222">Nel campo Nome digitare "ProcessingDateTime".</span><span class="sxs-lookup"><span data-stu-id="b027d-222">In the Name field, type 'ProcessingDateTime'.</span></span>
    * <span data-ttu-id="b027d-223">ProcessingDateTime</span><span class="sxs-lookup"><span data-stu-id="b027d-223">ProcessingDateTime</span></span>  
62. <span data-ttu-id="b027d-224">Nel campo Etichetta immettere "Data e ora di elaborazione".</span><span class="sxs-lookup"><span data-stu-id="b027d-224">In the Label field, enter 'Processing date & time'.</span></span>
    * <span data-ttu-id="b027d-225">Data e ora di elaborazione</span><span class="sxs-lookup"><span data-stu-id="b027d-225">Processing date & time</span></span>  
63. <span data-ttu-id="b027d-226">Fare clic su Modifica formula.</span><span class="sxs-lookup"><span data-stu-id="b027d-226">Click Edit formula.</span></span>
64. <span data-ttu-id="b027d-227">Nella struttura selezionare 'Data/ora\SESSIONNOW'.</span><span class="sxs-lookup"><span data-stu-id="b027d-227">In the tree, select 'Date/time\SESSIONNOW'.</span></span>
65. <span data-ttu-id="b027d-228">Fare clic su Aggiungi funzione.</span><span class="sxs-lookup"><span data-stu-id="b027d-228">Click Add function.</span></span>
66. <span data-ttu-id="b027d-229">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="b027d-229">Click Save.</span></span>
67. <span data-ttu-id="b027d-230">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="b027d-230">Close the page.</span></span>
68. <span data-ttu-id="b027d-231">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="b027d-231">Click OK.</span></span>
    * <span data-ttu-id="b027d-232">Aggiungere il campo calcolato ProcessingDateTime come origine dati per il modello dati corrente.</span><span class="sxs-lookup"><span data-stu-id="b027d-232">Add the ProcessingDateTime calculated field as a data source for the current data model.</span></span>  
69. <span data-ttu-id="b027d-233">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="b027d-233">Click Save.</span></span>
70. <span data-ttu-id="b027d-234">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="b027d-234">Close the page.</span></span>
71. <span data-ttu-id="b027d-235">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="b027d-235">Close the page.</span></span>
72. <span data-ttu-id="b027d-236">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="b027d-236">Close the page.</span></span>

