--- 
title: Mappare un modello dati alle origini dati selezionate per la creazione di report elettronici (ER)
description: "I passaggi seguenti descrivono come un utente con ruolo amministratore di sistema o sviluppatore per la creazione di report elettronici può mappare un modello dati per la creazione di report elettronici a origini dati di Dynamics 365 for Finance and Operations, Enterprise edition (novembre 2016) selezionate."
author: NickSelin
manager: AnnBe
ms.date: 01/16/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 326e535c9c01812a399da932c414a73ad0ee3bc6
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---
# <a name="map-a-data-model-to-selected-data-sources-for-electronic-reporting-er"></a><span data-ttu-id="84d11-103">Mappare un modello dati alle origini dati selezionate per la creazione di report elettronici (ER)</span><span class="sxs-lookup"><span data-stu-id="84d11-103">Map a data model to selected data sources for electronic reporting (ER)</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="84d11-104">I passaggi seguenti descrivono come un utente con ruolo amministratore di sistema o sviluppatore per la creazione di report elettronici può mappare un modello dati per la creazione di report elettronici a origini dati di Dynamics 365 for Finance and Operations selezionate.</span><span class="sxs-lookup"><span data-stu-id="84d11-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can map an Electronic reporting (ER) data model to selected Dynamics 365 for Finance and Operations data sources.</span></span> <span data-ttu-id="84d11-105">Il mapping di modello verrà utilizzato in seguito come origine dati in un formato di configurazione da utilizzare per gestire i documenti di pagamento elettronico.</span><span class="sxs-lookup"><span data-stu-id="84d11-105">This model mapping will later be used as a data source in a format configuration that will be used to manage electronic payment documents.</span></span> <span data-ttu-id="84d11-106">In questo esempio si esegue il mapping di modello dati per la società di esempio, Litware, Inc. alle origini dati.</span><span class="sxs-lookup"><span data-stu-id="84d11-106">In this example, you map a data model for sample company, Litware, Inc. to data sources.</span></span> <span data-ttu-id="84d11-107">Per completare questi passaggi, è necessario aver completato prima i passaggi della procedura "Selezionare le origini dati per il mapping di modello".</span><span class="sxs-lookup"><span data-stu-id="84d11-107">To complete these steps, you must first complete the steps in the “Select data sources for model mapping” procedure.</span></span>


## <a name="open-er-configurations-tree"></a><span data-ttu-id="84d11-108">Consente di aprire la struttura di configurazioni per la creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="84d11-108">Open ER configurations tree</span></span>
1. <span data-ttu-id="84d11-109">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="84d11-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="84d11-110">Fare clic Configurazioni:</span><span class="sxs-lookup"><span data-stu-id="84d11-110">Click Configurations.</span></span>

## <a name="select-created-model-mapping"></a><span data-ttu-id="84d11-111">Selezionare il mapping del modello creato</span><span class="sxs-lookup"><span data-stu-id="84d11-111">Select created model mapping</span></span>
1. <span data-ttu-id="84d11-112">Nella struttura selezionare "Pagamenti (modello semplificato)".</span><span class="sxs-lookup"><span data-stu-id="84d11-112">In the tree, select 'Payments (simplified model)'.</span></span>
    * <span data-ttu-id="84d11-113">Verificare che la configurazione del modello "Pagamenti (modello semplificato)" sia stata creata in anticipo.</span><span class="sxs-lookup"><span data-stu-id="84d11-113">Make sure that the model configuration “Payments (simplified model)” has been created in advance.</span></span> <span data-ttu-id="84d11-114">In caso contrario, arrestare ora e tornare al termine della guida attività 'Creare una nuova configurazione con il modello dati del dominio selezionato'.</span><span class="sxs-lookup"><span data-stu-id="84d11-114">Otherwise, stop now and return after completion of the task guide ‘Create a new configuration with data model of the selected domain’.</span></span>  
2. <span data-ttu-id="84d11-115">Fare clic su Progettazione modello.</span><span class="sxs-lookup"><span data-stu-id="84d11-115">Click Model designer.</span></span>
3. <span data-ttu-id="84d11-116">Fare clic su Mappa modello a origine dati.</span><span class="sxs-lookup"><span data-stu-id="84d11-116">Click Map model to datasource.</span></span>
4. <span data-ttu-id="84d11-117">Selezionare il record "Mapping bonifico".</span><span class="sxs-lookup"><span data-stu-id="84d11-117">Select the 'CT mapping' record.</span></span>
    * <span data-ttu-id="84d11-118">Mapping bonifico</span><span class="sxs-lookup"><span data-stu-id="84d11-118">CT mapping</span></span>  

## <a name="bind-created-data-sources-to-data-model-elements"></a><span data-ttu-id="84d11-119">Associare le origini dati create a elementi del modello dati</span><span class="sxs-lookup"><span data-stu-id="84d11-119">Bind created data sources to data model elements</span></span>
1. <span data-ttu-id="84d11-120">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="84d11-120">Click Designer.</span></span>
2. <span data-ttu-id="84d11-121">Nella struttura selezionare "Data e ora di elaborazione(ProcessingDateTime)".</span><span class="sxs-lookup"><span data-stu-id="84d11-121">In the tree, select 'Processing date & time(ProcessingDateTime)'.</span></span>
3. <span data-ttu-id="84d11-122">Nella struttura selezionare "Data di elaborazione(ProcessingDateTime)".</span><span class="sxs-lookup"><span data-stu-id="84d11-122">In the tree, select 'Processing date(ProcessingDateTime)'.</span></span>
4. <span data-ttu-id="84d11-123">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="84d11-123">Click Bind.</span></span>
5. <span data-ttu-id="84d11-124">Nella struttura selezionare "Identificazione messaggio di pagamento(MessageIdentification)".</span><span class="sxs-lookup"><span data-stu-id="84d11-124">In the tree, select 'Payment message identification(MessageIdentification)'.</span></span>
6. <span data-ttu-id="84d11-125">Nella struttura espandere "Transazioni".</span><span class="sxs-lookup"><span data-stu-id="84d11-125">In the tree, expand 'Transactions'.</span></span>
7. <span data-ttu-id="84d11-126">Nella struttura selezionare "Transazioni\Numero batch giornale di registrazione(JournalNum)".</span><span class="sxs-lookup"><span data-stu-id="84d11-126">In the tree, select 'Transactions\Journal batch number(JournalNum)'.</span></span>
8. <span data-ttu-id="84d11-127">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="84d11-127">Click Bind.</span></span>
9. <span data-ttu-id="84d11-128">Nella struttura selezionare "Pagamenti".</span><span class="sxs-lookup"><span data-stu-id="84d11-128">In the tree, select 'Payments'.</span></span>
10. <span data-ttu-id="84d11-129">Nella struttura selezionare "Transazioni".</span><span class="sxs-lookup"><span data-stu-id="84d11-129">In the tree, select 'Transactions'.</span></span>
11. <span data-ttu-id="84d11-130">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="84d11-130">Click Bind.</span></span>
12. <span data-ttu-id="84d11-131">Nella struttura espandere "Pagamenti= Transazioni".</span><span class="sxs-lookup"><span data-stu-id="84d11-131">In the tree, expand 'Payments= Transactions'.</span></span>
13. <span data-ttu-id="84d11-132">Nella struttura espandere "Pagamenti= Transazioni\Creditore".</span><span class="sxs-lookup"><span data-stu-id="84d11-132">In the tree, expand 'Payments= Transactions\Creditor'.</span></span>
14. <span data-ttu-id="84d11-133">Nella struttura espandere "Pagamenti= Transazioni\Creditore\Conto".</span><span class="sxs-lookup"><span data-stu-id="84d11-133">In the tree, expand 'Payments= Transactions\Creditor\Account'.</span></span>
15. <span data-ttu-id="84d11-134">Nella struttura selezionare "Pagamenti= Transazioni\Creditore\Conto\Codice valuta(Currency)".</span><span class="sxs-lookup"><span data-stu-id="84d11-134">In the tree, select 'Payments= Transactions\Creditor\Account\Currency code(Currency)'.</span></span>
16. <span data-ttu-id="84d11-135">Nella struttura espandere "Transazioni\vendBankAccountInTransactionCompany()".</span><span class="sxs-lookup"><span data-stu-id="84d11-135">In the tree, expand 'Transactions\vendBankAccountInTransactionCompany()'.</span></span>
17. <span data-ttu-id="84d11-136">Nella struttura selezionare "Transazioni\vendBankAccountInTransactionCompany()\Valuta(CurrencyCode)".</span><span class="sxs-lookup"><span data-stu-id="84d11-136">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\Currency(CurrencyCode)'.</span></span>
18. <span data-ttu-id="84d11-137">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="84d11-137">Click Bind.</span></span>
19. <span data-ttu-id="84d11-138">Nella struttura selezionare "Pagamenti= Transazioni\Creditore\Conto\Codice IBAN(IBAN)".</span><span class="sxs-lookup"><span data-stu-id="84d11-138">In the tree, select 'Payments= Transactions\Creditor\Account\IBAN code(IBAN)'.</span></span>
20. <span data-ttu-id="84d11-139">Nella struttura selezionare "Transazioni\vendBankAccountInTransactionCompany()\IBAN(BankIBAN)".</span><span class="sxs-lookup"><span data-stu-id="84d11-139">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\IBAN(BankIBAN)'.</span></span>
21. <span data-ttu-id="84d11-140">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="84d11-140">Click Bind.</span></span>
22. <span data-ttu-id="84d11-141">Nella struttura selezionare "Pagamenti= Transazioni\Creditore\Conto\Numero".</span><span class="sxs-lookup"><span data-stu-id="84d11-141">In the tree, select 'Payments= Transactions\Creditor\Account\Number'.</span></span>
23. <span data-ttu-id="84d11-142">Nella struttura selezionare "Transazioni\vendBankAccountInTransactionCompany()\Numero conto bancario(AccountNum)".</span><span class="sxs-lookup"><span data-stu-id="84d11-142">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\Bank account number(AccountNum)'.</span></span>
24. <span data-ttu-id="84d11-143">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="84d11-143">Click Bind.</span></span>
25. <span data-ttu-id="84d11-144">Nella struttura espandere "Pagamenti= Transazioni\Creditore\Agente".</span><span class="sxs-lookup"><span data-stu-id="84d11-144">In the tree, expand 'Payments= Transactions\Creditor\Agent'.</span></span>
26. <span data-ttu-id="84d11-145">Nella struttura selezionare "Pagamenti= Transazioni\Creditore\Agente\Nome".</span><span class="sxs-lookup"><span data-stu-id="84d11-145">In the tree, select 'Payments= Transactions\Creditor\Agent\Name'.</span></span>
27. <span data-ttu-id="84d11-146">Nella struttura selezionare "Transazioni\vendBankAccountInTransactionCompany()\Nome".</span><span class="sxs-lookup"><span data-stu-id="84d11-146">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\Name'.</span></span>
28. <span data-ttu-id="84d11-147">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="84d11-147">Click Bind.</span></span>
29. <span data-ttu-id="84d11-148">Nella struttura selezionare "Pagamenti= Transazioni\Creditore\Agente\Numero di registrazione(RoutingNumber)".</span><span class="sxs-lookup"><span data-stu-id="84d11-148">In the tree, select 'Payments= Transactions\Creditor\Agent\Routing number(RoutingNumber)'.</span></span>
30. <span data-ttu-id="84d11-149">Nella struttura selezionare "Transazioni\vendBankAccountInTransactionCompany()\Numero di registrazione(RegistrationNum)".</span><span class="sxs-lookup"><span data-stu-id="84d11-149">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\Routing number(RegistrationNum)'.</span></span>
31. <span data-ttu-id="84d11-150">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="84d11-150">Click Bind.</span></span>
32. <span data-ttu-id="84d11-151">Nella struttura selezionare "Pagamenti= Transazioni\Creditore\Agente\Codice SWIFT(SWIFT)".</span><span class="sxs-lookup"><span data-stu-id="84d11-151">In the tree, select 'Payments= Transactions\Creditor\Agent\SWIFT code(SWIFT)'.</span></span>
33. <span data-ttu-id="84d11-152">Nella struttura selezionare "Transazioni\vendBankAccountInTransactionCompany()\Codice SWIFT(SWIFTNo)".</span><span class="sxs-lookup"><span data-stu-id="84d11-152">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\SWIFT code(SWIFTNo)'.</span></span>
34. <span data-ttu-id="84d11-153">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="84d11-153">Click Bind.</span></span>
35. <span data-ttu-id="84d11-154">Nella struttura selezionare "Pagamenti= Transazioni\Creditore\Nome".</span><span class="sxs-lookup"><span data-stu-id="84d11-154">In the tree, select 'Payments= Transactions\Creditor\Name'.</span></span>
36. <span data-ttu-id="84d11-155">Nella struttura espandere "Transazioni\findVendTable()".</span><span class="sxs-lookup"><span data-stu-id="84d11-155">In the tree, expand 'Transactions\findVendTable()'.</span></span>
37. <span data-ttu-id="84d11-156">Nella struttura selezionare "Transazioni\findVendTable()\name()".</span><span class="sxs-lookup"><span data-stu-id="84d11-156">In the tree, select 'Transactions\findVendTable()\name()'.</span></span>
38. <span data-ttu-id="84d11-157">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="84d11-157">Click Bind.</span></span>
39. <span data-ttu-id="84d11-158">Nella struttura selezionare "Pagamenti= Transazioni\Codice valuta(Currency)".</span><span class="sxs-lookup"><span data-stu-id="84d11-158">In the tree, select 'Payments= Transactions\Currency code(Currency)'.</span></span>
40. <span data-ttu-id="84d11-159">Nella struttura, espandere "Transazioni\>Relazioni".</span><span class="sxs-lookup"><span data-stu-id="84d11-159">In the tree, expand 'Transactions\>Relations'.</span></span>
41. <span data-ttu-id="84d11-160">Nella struttura, espandere "Transazioni\>Relazioni\Tabella valute(Currency)".</span><span class="sxs-lookup"><span data-stu-id="84d11-160">In the tree, expand 'Transactions\>Relations\Currency table(Currency)'.</span></span>
42. <span data-ttu-id="84d11-161">Nella struttura, selezionare "Transazioni\>Relazioni\Tabella valute(Currency)\Codice valuta(CurrencyCodeISO)".</span><span class="sxs-lookup"><span data-stu-id="84d11-161">In the tree, select 'Transactions\>Relations\Currency table(Currency)\Currency code(CurrencyCodeISO)'.</span></span>
43. <span data-ttu-id="84d11-162">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="84d11-162">Click Bind.</span></span>
44. <span data-ttu-id="84d11-163">Nella struttura espandere "Pagamenti= Transazioni\Debitore".</span><span class="sxs-lookup"><span data-stu-id="84d11-163">In the tree, expand 'Payments= Transactions\Debtor'.</span></span>
45. <span data-ttu-id="84d11-164">Nella struttura espandere "Pagamenti= Transazioni\Debitore\Conto".</span><span class="sxs-lookup"><span data-stu-id="84d11-164">In the tree, expand 'Payments= Transactions\Debtor\Account'.</span></span>
46. <span data-ttu-id="84d11-165">Nella struttura selezionare "Pagamenti= Transazioni\Debitore\Conto\Codice valuta(Currency)".</span><span class="sxs-lookup"><span data-stu-id="84d11-165">In the tree, select 'Payments= Transactions\Debtor\Account\Currency code(Currency)'.</span></span>
47. <span data-ttu-id="84d11-166">Nella struttura selezionare "Conto bancario(BankAccount)".</span><span class="sxs-lookup"><span data-stu-id="84d11-166">In the tree, select 'Bank Account(BankAccount)'.</span></span>
48. <span data-ttu-id="84d11-167">Nella struttura espandere "Conto bancario(BankAccount)".</span><span class="sxs-lookup"><span data-stu-id="84d11-167">In the tree, expand 'Bank Account(BankAccount)'.</span></span>
49. <span data-ttu-id="84d11-168">Nella struttura selezionare "Conto bancario(BankAccount)\Valuta(CurrencyCode)".</span><span class="sxs-lookup"><span data-stu-id="84d11-168">In the tree, select 'Bank Account(BankAccount)\Currency(CurrencyCode)'.</span></span>
50. <span data-ttu-id="84d11-169">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="84d11-169">Click Bind.</span></span>
51. <span data-ttu-id="84d11-170">Nella struttura selezionare "Conto bancario(BankAccount)\IBAN".</span><span class="sxs-lookup"><span data-stu-id="84d11-170">In the tree, select 'Bank Account(BankAccount)\IBAN'.</span></span>
52. <span data-ttu-id="84d11-171">Nella struttura selezionare "Pagamenti= Transazioni\Debitore\Conto\Codice IBAN(IBAN)".</span><span class="sxs-lookup"><span data-stu-id="84d11-171">In the tree, select 'Payments= Transactions\Debtor\Account\IBAN code(IBAN)'.</span></span>
53. <span data-ttu-id="84d11-172">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="84d11-172">Click Bind.</span></span>
54. <span data-ttu-id="84d11-173">Nella struttura selezionare "Pagamenti= Transazioni\Debitore\Conto\Numero".</span><span class="sxs-lookup"><span data-stu-id="84d11-173">In the tree, select 'Payments= Transactions\Debtor\Account\Number'.</span></span>
55. <span data-ttu-id="84d11-174">Nella struttura selezionare "Conto bancario(BankAccount)\Numero conto bancario(AccountNum)".</span><span class="sxs-lookup"><span data-stu-id="84d11-174">In the tree, select 'Bank Account(BankAccount)\Bank account number(AccountNum)'.</span></span>
56. <span data-ttu-id="84d11-175">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="84d11-175">Click Bind.</span></span>
57. <span data-ttu-id="84d11-176">Nella struttura espandere "Pagamenti= Transazioni\Debitore\Agente".</span><span class="sxs-lookup"><span data-stu-id="84d11-176">In the tree, expand 'Payments= Transactions\Debtor\Agent'.</span></span>
58. <span data-ttu-id="84d11-177">Nella struttura selezionare "Pagamenti= Transazioni\Debitore\Agente\Nome".</span><span class="sxs-lookup"><span data-stu-id="84d11-177">In the tree, select 'Payments= Transactions\Debtor\Agent\Name'.</span></span>
59. <span data-ttu-id="84d11-178">Nella struttura selezionare "Conto bancario(BankAccount)\Nome".</span><span class="sxs-lookup"><span data-stu-id="84d11-178">In the tree, select 'Bank Account(BankAccount)\Name'.</span></span>
60. <span data-ttu-id="84d11-179">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="84d11-179">Click Bind.</span></span>
61. <span data-ttu-id="84d11-180">Nella struttura selezionare "Pagamenti= Transazioni\Debitore\Agente\Numero di registrazione(RoutingNumber)".</span><span class="sxs-lookup"><span data-stu-id="84d11-180">In the tree, select 'Payments= Transactions\Debtor\Agent\Routing number(RoutingNumber)'.</span></span>
62. <span data-ttu-id="84d11-181">Nella struttura selezionare "Conto bancario(BankAccount)\Numero di registrazione(RegistrationNum)".</span><span class="sxs-lookup"><span data-stu-id="84d11-181">In the tree, select 'Bank Account(BankAccount)\Routing number(RegistrationNum)'.</span></span>
63. <span data-ttu-id="84d11-182">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="84d11-182">Click Bind.</span></span>
64. <span data-ttu-id="84d11-183">Nella struttura selezionare "Pagamenti= Transazioni\Debitore\Agente\Codice SWIFT(SWIFT)".</span><span class="sxs-lookup"><span data-stu-id="84d11-183">In the tree, select 'Payments= Transactions\Debtor\Agent\SWIFT code(SWIFT)'.</span></span>
65. <span data-ttu-id="84d11-184">Nella struttura selezionare "Conto bancario(BankAccount)\Codice SWIFT(SWIFTNo)".</span><span class="sxs-lookup"><span data-stu-id="84d11-184">In the tree, select 'Bank Account(BankAccount)\SWIFT code(SWIFTNo)'.</span></span>
66. <span data-ttu-id="84d11-185">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="84d11-185">Click Bind.</span></span>
67. <span data-ttu-id="84d11-186">Nella struttura selezionare "Pagamenti= Transazioni\Debitore\Nome".</span><span class="sxs-lookup"><span data-stu-id="84d11-186">In the tree, select 'Payments= Transactions\Debtor\Name'.</span></span>
68. <span data-ttu-id="84d11-187">Nella struttura selezionare "Informazioni società(Company)".</span><span class="sxs-lookup"><span data-stu-id="84d11-187">In the tree, select 'Company information(Company)'.</span></span>
69. <span data-ttu-id="84d11-188">Nella struttura espandere "Informazioni società(Company)".</span><span class="sxs-lookup"><span data-stu-id="84d11-188">In the tree, expand 'Company information(Company)'.</span></span>
70. <span data-ttu-id="84d11-189">Nella struttura selezionare "Informazioni società(Company)\Nome".</span><span class="sxs-lookup"><span data-stu-id="84d11-189">In the tree, select 'Company information(Company)\Name'.</span></span>
71. <span data-ttu-id="84d11-190">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="84d11-190">Click Bind.</span></span>
72. <span data-ttu-id="84d11-191">Nella struttura selezionare "Pagamenti= Transazioni\Descrizione".</span><span class="sxs-lookup"><span data-stu-id="84d11-191">In the tree, select 'Payments= Transactions\Description'.</span></span>
73. <span data-ttu-id="84d11-192">Nella struttura selezionare "Transazioni\Descrizione(Txt)".</span><span class="sxs-lookup"><span data-stu-id="84d11-192">In the tree, select 'Transactions\Description(Txt)'.</span></span>
74. <span data-ttu-id="84d11-193">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="84d11-193">Click Bind.</span></span>
75. <span data-ttu-id="84d11-194">Nella struttura selezionare "Pagamenti= Transazioni\Codice di identificazione end-to-end(End2EndID)".</span><span class="sxs-lookup"><span data-stu-id="84d11-194">In the tree, select 'Payments= Transactions\End to end identification code(End2EndID)'.</span></span>
76. <span data-ttu-id="84d11-195">Nella struttura, selezionare "Transazioni\$EndToEndID".</span><span class="sxs-lookup"><span data-stu-id="84d11-195">In the tree, select 'Transactions\$EndToEndID'.</span></span>
77. <span data-ttu-id="84d11-196">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="84d11-196">Click Bind.</span></span>
78. <span data-ttu-id="84d11-197">Nella struttura selezionare "Pagamenti= Transazioni\Importo istruito(InstructedAmount)".</span><span class="sxs-lookup"><span data-stu-id="84d11-197">In the tree, select 'Payments= Transactions\Instructed amount(InstructedAmount)'.</span></span>
79. <span data-ttu-id="84d11-198">Nella struttura selezionare "Transazioni\$Amount".</span><span class="sxs-lookup"><span data-stu-id="84d11-198">In the tree, select 'Transactions\$Amount'.</span></span>
80. <span data-ttu-id="84d11-199">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="84d11-199">Click Bind.</span></span>
81. <span data-ttu-id="84d11-200">Nella struttura selezionare "Pagamenti= Transazioni\Data della transazione(TransactionDate)".</span><span class="sxs-lookup"><span data-stu-id="84d11-200">In the tree, select 'Payments= Transactions\Transaction date(TransactionDate)'.</span></span>
82. <span data-ttu-id="84d11-201">Nella struttura selezionare "Transazioni\Data(TransDate)".</span><span class="sxs-lookup"><span data-stu-id="84d11-201">In the tree, select 'Transactions\Date(TransDate)'.</span></span>
83. <span data-ttu-id="84d11-202">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="84d11-202">Click Bind.</span></span>

## <a name="validate-created-mapping"></a><span data-ttu-id="84d11-203">Convalida il mapping creato</span><span class="sxs-lookup"><span data-stu-id="84d11-203">Validate created mapping</span></span>
1. <span data-ttu-id="84d11-204">Fare clic su Convalida.</span><span class="sxs-lookup"><span data-stu-id="84d11-204">Click Validate.</span></span>
    * <span data-ttu-id="84d11-205">Convalidare il nuovo mapping per assicurarsi che tutte le associazioni siano corrette.</span><span class="sxs-lookup"><span data-stu-id="84d11-205">Validate the new mapping to ensure that all bindings are okay.</span></span>  
2. <span data-ttu-id="84d11-206">Fare clic sulla freccia per espandere o comprimere la sezione Elenco errori.</span><span class="sxs-lookup"><span data-stu-id="84d11-206">Click the arrow to expand or collapse the Error List section.</span></span>
3. <span data-ttu-id="84d11-207">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="84d11-207">Click Save.</span></span>
4. <span data-ttu-id="84d11-208">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="84d11-208">Close the page.</span></span>
5. <span data-ttu-id="84d11-209">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="84d11-209">Close the page.</span></span>
6. <span data-ttu-id="84d11-210">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="84d11-210">Close the page.</span></span>

## <a name="change-the-status-of-the-current-version-of-model-configuration"></a><span data-ttu-id="84d11-211">Modificare lo stato della versione corrente della configurazione del modello</span><span class="sxs-lookup"><span data-stu-id="84d11-211">Change the status of the current version of model configuration</span></span>
1. <span data-ttu-id="84d11-212">Fare clic su Cambia stato.</span><span class="sxs-lookup"><span data-stu-id="84d11-212">Click Change status.</span></span>
    * <span data-ttu-id="84d11-213">Modificare lo stato della configurazione designata del modello da Bozza a Completato per renderla disponibile per la progettazione del formato di pagamento.</span><span class="sxs-lookup"><span data-stu-id="84d11-213">Change the status of designed model configuration – from Draft to Completed to make it available for payment format design.</span></span>  
2. <span data-ttu-id="84d11-214">Fare clic su Completa.</span><span class="sxs-lookup"><span data-stu-id="84d11-214">Click Complete.</span></span>
    * <span data-ttu-id="84d11-215">Seleziona Completa.</span><span class="sxs-lookup"><span data-stu-id="84d11-215">Select Complete.</span></span>  
3. <span data-ttu-id="84d11-216">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="84d11-216">In the Description field, type a value.</span></span>
    * <span data-ttu-id="84d11-217">Ad esempio, 'versione 1'.</span><span class="sxs-lookup"><span data-stu-id="84d11-217">For example, 'version 1'.</span></span>  
4. <span data-ttu-id="84d11-218">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="84d11-218">Click OK.</span></span>
5. <span data-ttu-id="84d11-219">Selezionare la versione completata della configurazione corrente.</span><span class="sxs-lookup"><span data-stu-id="84d11-219">Select the completed version of the current configuration.</span></span>
    * <span data-ttu-id="84d11-220">Si noti che la configurazione creata viene salvata come versione completata 1.</span><span class="sxs-lookup"><span data-stu-id="84d11-220">Note that the created configuration is saved as completed version 1.</span></span>  


