--- 
title: Progettare un modello di dati specifico del dominio per la creazione di report elettronici (ER)
description: "I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare una nuova configurazione per la creazione di report elettronici che contiene un modello dati per i documenti di pagamento elettronico."
author: NickSelin
manager: AnnBe
ms.date: 12/21/2016
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
ms.openlocfilehash: 6a9fff90af93e20e7f812022593d25963542fac1
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---
# <a name="design-a-domain-specific-data-model-for-electronic-reporting-er"></a><span data-ttu-id="15f3e-103">Progettare un modello di dati specifico del dominio per la creazione di report elettronici (ER)</span><span class="sxs-lookup"><span data-stu-id="15f3e-103">Design a domain-specific data model for electronic reporting (ER)</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="15f3e-104">I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare una nuova configurazione per la creazione di report elettronici che contiene un modello dati per i documenti di pagamento elettronico.</span><span class="sxs-lookup"><span data-stu-id="15f3e-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="15f3e-105">Questo modello dati verrà utilizzato successivamente come origine dati quando si crea il formato dei documenti di pagamento.</span><span class="sxs-lookup"><span data-stu-id="15f3e-105">This data model will later be used as a data source when you create the format of the payment documents.</span></span>



<span data-ttu-id="15f3e-106">In questo esempio verrà creata una configurazione per la società di esempio Litware, Inc. Queste operazioni possono essere eseguite in qualsiasi società perché le configurazioni per la creazione di report elettronici sono condivise tra tutte le società.</span><span class="sxs-lookup"><span data-stu-id="15f3e-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="15f3e-107">Per completare questi passaggi, è necessario completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".</span><span class="sxs-lookup"><span data-stu-id="15f3e-107">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>

1. <span data-ttu-id="15f3e-108">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="15f3e-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="15f3e-109">Selezionare il provider di configurazione per la società di esempio Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="15f3e-109">Select the configuration provider for sample company, ‘Litware, Inc.’</span></span> <span data-ttu-id="15f3e-110">Se il provider di configurazione non viene visualizzato, è necessario innanzitutto completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".</span><span class="sxs-lookup"><span data-stu-id="15f3e-110">If you don’t see this configuration provider, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>  
2. <span data-ttu-id="15f3e-111">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="15f3e-111">Click Reporting configurations.</span></span>
    * <span data-ttu-id="15f3e-112">Verrà creata una configurazione che contiene un modello dati per i documenti di pagamento elettronico.</span><span class="sxs-lookup"><span data-stu-id="15f3e-112">You will create a configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="15f3e-113">Questo modello dati verrà utilizzato successivamente come origine dati quando si crea il formato dei documenti di pagamento.</span><span class="sxs-lookup"><span data-stu-id="15f3e-113">This data model will be used later as a data source when you create the format for the payment documents.</span></span>  

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="15f3e-114">Crea una nuova configurazione di modello dati</span><span class="sxs-lookup"><span data-stu-id="15f3e-114">Create a new data model configuration</span></span>
1. <span data-ttu-id="15f3e-115">Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .</span><span class="sxs-lookup"><span data-stu-id="15f3e-115">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="15f3e-116">Nel campo Nome digitare "Pagamenti (modello semplificato)".</span><span class="sxs-lookup"><span data-stu-id="15f3e-116">In the Name field, type 'Payments (simplified model)'.</span></span>
    * <span data-ttu-id="15f3e-117">Pagamenti (modello semplificato)</span><span class="sxs-lookup"><span data-stu-id="15f3e-117">Payments (simplified model)</span></span>  
3. <span data-ttu-id="15f3e-118">Nel campo Descrizione digitare "Configurazione modello di pagamento".</span><span class="sxs-lookup"><span data-stu-id="15f3e-118">In the Description field, type 'Payment model configuration'.</span></span>
    * <span data-ttu-id="15f3e-119">Configurazione modello di pagamento</span><span class="sxs-lookup"><span data-stu-id="15f3e-119">Payment model configuration</span></span>  
    * <span data-ttu-id="15f3e-120">Il provider di configurazione attiva viene inserito automaticamente in questo punto.</span><span class="sxs-lookup"><span data-stu-id="15f3e-120">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="15f3e-121">Tale provider potrà gestire la configurazione.</span><span class="sxs-lookup"><span data-stu-id="15f3e-121">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="15f3e-122">Altri provider possono utilizzare la configurazione, ma non potranno gestirla.</span><span class="sxs-lookup"><span data-stu-id="15f3e-122">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
4. <span data-ttu-id="15f3e-123">Fare clic sul pulsante "Crea configurazione" per completare l'attività di creazione della configurazione</span><span class="sxs-lookup"><span data-stu-id="15f3e-123">Click ‘Create configuration’ button to complete the configuration creation task</span></span>

## <a name="create-a-data-model"></a><span data-ttu-id="15f3e-124">Creare un modello dati</span><span class="sxs-lookup"><span data-stu-id="15f3e-124">Create a data model</span></span>
    * <span data-ttu-id="15f3e-125">Si sta creando un nuovo modello dati per la configurazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="15f3e-125">You're creating a new data model for the selected configuration.</span></span> <span data-ttu-id="15f3e-126">Questa versione di configurazione avrà lo stato di bozza.</span><span class="sxs-lookup"><span data-stu-id="15f3e-126">This configuration version will have a status of Draft.</span></span>  
1. <span data-ttu-id="15f3e-127">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="15f3e-127">Click Designer.</span></span>

## <a name="define-the-structure-of-a-party-participating-in-a-payment-process"></a><span data-ttu-id="15f3e-128">Definire la struttura di una parte che partecipa a un processo di pagamento</span><span class="sxs-lookup"><span data-stu-id="15f3e-128">Define the structure of a party participating in a payment process</span></span>
1. <span data-ttu-id="15f3e-129">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="15f3e-129">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="15f3e-130">Digitare 'Party' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="15f3e-130">In the Name field, type 'Party'.</span></span>
    * <span data-ttu-id="15f3e-131">Parte</span><span class="sxs-lookup"><span data-stu-id="15f3e-131">Party</span></span>  
3. <span data-ttu-id="15f3e-132">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="15f3e-132">Click Add.</span></span>
4. <span data-ttu-id="15f3e-133">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="15f3e-133">Click New to open the drop dialog.</span></span>
5. <span data-ttu-id="15f3e-134">Nel campo Nome digitare "Nome".</span><span class="sxs-lookup"><span data-stu-id="15f3e-134">In the Name field, type 'Name'.</span></span>
    * <span data-ttu-id="15f3e-135">Nome</span><span class="sxs-lookup"><span data-stu-id="15f3e-135">Name</span></span>  
6. <span data-ttu-id="15f3e-136">Nel campo Tipo di articolo selezionare "Stringa".</span><span class="sxs-lookup"><span data-stu-id="15f3e-136">In the Item type field, select 'String'.</span></span>
7. <span data-ttu-id="15f3e-137">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="15f3e-137">Click Add.</span></span>
8. <span data-ttu-id="15f3e-138">Digitare 'Party' nel campo Trova.</span><span class="sxs-lookup"><span data-stu-id="15f3e-138">In the Find field, type 'Party'.</span></span>
    * <span data-ttu-id="15f3e-139">Parte</span><span class="sxs-lookup"><span data-stu-id="15f3e-139">Party</span></span>  
9. <span data-ttu-id="15f3e-140">Fare clic su Trova precedente.</span><span class="sxs-lookup"><span data-stu-id="15f3e-140">Click Find previous.</span></span>

## <a name="define-the-bank-structure-for-this-model"></a><span data-ttu-id="15f3e-141">Definire la struttura della banca per il modello</span><span class="sxs-lookup"><span data-stu-id="15f3e-141">Define the bank structure for this model</span></span>
1. <span data-ttu-id="15f3e-142">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="15f3e-142">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="15f3e-143">Nel campo Nome digitare "Agente".</span><span class="sxs-lookup"><span data-stu-id="15f3e-143">In the Name field, type 'Agent'.</span></span>
    * <span data-ttu-id="15f3e-144">Agente</span><span class="sxs-lookup"><span data-stu-id="15f3e-144">Agent</span></span>  
3. <span data-ttu-id="15f3e-145">Nel campo Tipo di articolo selezionare "Record".</span><span class="sxs-lookup"><span data-stu-id="15f3e-145">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="15f3e-146">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="15f3e-146">Click Add.</span></span>
5. <span data-ttu-id="15f3e-147">Nel campo Descrizione immettere 'Istituto finanziario, ad esempio una banca, responsabile di un conto per la parte (debitore/creditore).'.</span><span class="sxs-lookup"><span data-stu-id="15f3e-147">In the Description field, enter 'Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).'.</span></span>
    * <span data-ttu-id="15f3e-148">Istituto finanziario, ad esempio una banca, responsabile di un conto per la parte (debitore/creditore).</span><span class="sxs-lookup"><span data-stu-id="15f3e-148">Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).</span></span>  
6. <span data-ttu-id="15f3e-149">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="15f3e-149">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="15f3e-150">Nel campo Nome digitare "Nome".</span><span class="sxs-lookup"><span data-stu-id="15f3e-150">In the Name field, type 'Name'.</span></span>
    * <span data-ttu-id="15f3e-151">Nome</span><span class="sxs-lookup"><span data-stu-id="15f3e-151">Name</span></span>  
8. <span data-ttu-id="15f3e-152">Nel campo Tipo di articolo selezionare "Stringa".</span><span class="sxs-lookup"><span data-stu-id="15f3e-152">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="15f3e-153">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="15f3e-153">Click Add.</span></span>
10. <span data-ttu-id="15f3e-154">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="15f3e-154">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="15f3e-155">Nel campo Nome digitare "SWIFT".</span><span class="sxs-lookup"><span data-stu-id="15f3e-155">In the Name field, type 'SWIFT'.</span></span>
    * <span data-ttu-id="15f3e-156">SWIFT</span><span class="sxs-lookup"><span data-stu-id="15f3e-156">SWIFT</span></span>  
12. <span data-ttu-id="15f3e-157">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="15f3e-157">Click Add.</span></span>
13. <span data-ttu-id="15f3e-158">Nel campo Descrizione immettere 'Codice di identificazione bancario'.</span><span class="sxs-lookup"><span data-stu-id="15f3e-158">In the Description field, enter 'Bank identification code'.</span></span>
    * <span data-ttu-id="15f3e-159">Codice di identificazione bancario</span><span class="sxs-lookup"><span data-stu-id="15f3e-159">Bank identification code</span></span>  
14. <span data-ttu-id="15f3e-160">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="15f3e-160">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="15f3e-161">Nel campo Nome digitare "RoutingNumber".</span><span class="sxs-lookup"><span data-stu-id="15f3e-161">In the Name field, type 'RoutingNumber'.</span></span>
    * <span data-ttu-id="15f3e-162">RoutingNumber</span><span class="sxs-lookup"><span data-stu-id="15f3e-162">RoutingNumber</span></span>  
16. <span data-ttu-id="15f3e-163">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="15f3e-163">Click Add.</span></span>
17. <span data-ttu-id="15f3e-164">Nel campo Descrizione immettere 'Numero di registrazione'.</span><span class="sxs-lookup"><span data-stu-id="15f3e-164">In the Description field, enter 'Routing number'.</span></span>
    * <span data-ttu-id="15f3e-165">Numero di registrazione</span><span class="sxs-lookup"><span data-stu-id="15f3e-165">Routing number</span></span>  
18. <span data-ttu-id="15f3e-166">Fare clic su Trova precedente.</span><span class="sxs-lookup"><span data-stu-id="15f3e-166">Click Find previous.</span></span>

## <a name="define-the-bank-account-structure-for-this-model"></a><span data-ttu-id="15f3e-167">Definire la struttura del conto bancario per il modello</span><span class="sxs-lookup"><span data-stu-id="15f3e-167">Define the bank account structure for this model</span></span>
1. <span data-ttu-id="15f3e-168">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="15f3e-168">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="15f3e-169">Nel campo Nome digitare "Conto".</span><span class="sxs-lookup"><span data-stu-id="15f3e-169">In the Name field, type 'Account'.</span></span>
    * <span data-ttu-id="15f3e-170">Conto</span><span class="sxs-lookup"><span data-stu-id="15f3e-170">Account</span></span>  
3. <span data-ttu-id="15f3e-171">Nel campo Tipo di articolo selezionare "Record".</span><span class="sxs-lookup"><span data-stu-id="15f3e-171">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="15f3e-172">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="15f3e-172">Click Add.</span></span>
5. <span data-ttu-id="15f3e-173">Nel campo Descrizione, immettere 'Identificazione di un conto di una parte di un istituto finanziario, ad esempio una banca.'.</span><span class="sxs-lookup"><span data-stu-id="15f3e-173">In the Description field, enter 'Identification of an account of a party in a financial institution (for instance, a bank).'.</span></span>
    * <span data-ttu-id="15f3e-174">Identificazione di un conto di una parte di un istituto finanziario, ad esempio una banca.</span><span class="sxs-lookup"><span data-stu-id="15f3e-174">Identification of an account of a party in a financial institution (for instance, a bank).</span></span>  
6. <span data-ttu-id="15f3e-175">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="15f3e-175">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="15f3e-176">Nel campo Nome digitare "Valuta".</span><span class="sxs-lookup"><span data-stu-id="15f3e-176">In the Name field, type 'Currency'.</span></span>
    * <span data-ttu-id="15f3e-177">Valuta</span><span class="sxs-lookup"><span data-stu-id="15f3e-177">Currency</span></span>  
8. <span data-ttu-id="15f3e-178">Nel campo Tipo di articolo selezionare "Stringa".</span><span class="sxs-lookup"><span data-stu-id="15f3e-178">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="15f3e-179">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="15f3e-179">Click Add.</span></span>
10. <span data-ttu-id="15f3e-180">Nel campo Descrizione immettere 'Codice valuta'.</span><span class="sxs-lookup"><span data-stu-id="15f3e-180">In the Description field, enter 'Currency code'.</span></span>
    * <span data-ttu-id="15f3e-181">Codice valuta</span><span class="sxs-lookup"><span data-stu-id="15f3e-181">Currency code</span></span>  
11. <span data-ttu-id="15f3e-182">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="15f3e-182">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="15f3e-183">Nel campo Nome digitare "Numero".</span><span class="sxs-lookup"><span data-stu-id="15f3e-183">In the Name field, type 'Number'.</span></span>
    * <span data-ttu-id="15f3e-184">Numero</span><span class="sxs-lookup"><span data-stu-id="15f3e-184">Number</span></span>  
13. <span data-ttu-id="15f3e-185">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="15f3e-185">Click Add.</span></span>
14. <span data-ttu-id="15f3e-186">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="15f3e-186">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="15f3e-187">Nel campo nome digitare "IBAN".</span><span class="sxs-lookup"><span data-stu-id="15f3e-187">In the Name field, type 'IBAN'.</span></span>
    * <span data-ttu-id="15f3e-188">IBAN</span><span class="sxs-lookup"><span data-stu-id="15f3e-188">IBAN</span></span>  
16. <span data-ttu-id="15f3e-189">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="15f3e-189">Click Add.</span></span>
17. <span data-ttu-id="15f3e-190">Nel campo Descrizione immettere 'International Bank Account Number (numero di conto bancario internazionale)'.</span><span class="sxs-lookup"><span data-stu-id="15f3e-190">In the Description field, enter 'International bank account number'.</span></span>
    * <span data-ttu-id="15f3e-191">International Bank Account Number (numero di conto bancario internazionale)</span><span class="sxs-lookup"><span data-stu-id="15f3e-191">International bank account number</span></span>  

## <a name="define-the-payment-message-structure-for-credit-transfer-payment-type"></a><span data-ttu-id="15f3e-192">Definire la struttura del messaggio di pagamento per il tipo di pagamento con bonifico</span><span class="sxs-lookup"><span data-stu-id="15f3e-192">Define the payment message structure for credit transfer payment type</span></span>
1. <span data-ttu-id="15f3e-193">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="15f3e-193">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="15f3e-194">Nel campo Nuovo nodo come immettere 'Radice modello'.</span><span class="sxs-lookup"><span data-stu-id="15f3e-194">In the New node as a field, enter 'Model root'.</span></span>
3. <span data-ttu-id="15f3e-195">Nel campo Nome digitare "CustomerCreditTransferInitiation".</span><span class="sxs-lookup"><span data-stu-id="15f3e-195">In the Name field, type 'CustomerCreditTransferInitiation'.</span></span>
    * <span data-ttu-id="15f3e-196">CustomerCreditTransferInitiation</span><span class="sxs-lookup"><span data-stu-id="15f3e-196">CustomerCreditTransferInitiation</span></span>  
4. <span data-ttu-id="15f3e-197">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="15f3e-197">Click Add.</span></span>
5. <span data-ttu-id="15f3e-198">Nel campo Trova digitare 'CustomerCreditTransferInitiation'.</span><span class="sxs-lookup"><span data-stu-id="15f3e-198">In the Find field, type 'CustomerCreditTransferInitiation'.</span></span>
    * <span data-ttu-id="15f3e-199">CustomerCreditTransferInitiation</span><span class="sxs-lookup"><span data-stu-id="15f3e-199">CustomerCreditTransferInitiation</span></span>  
6. <span data-ttu-id="15f3e-200">Fare clic su Trova precedente.</span><span class="sxs-lookup"><span data-stu-id="15f3e-200">Click Find previous.</span></span>
7. <span data-ttu-id="15f3e-201">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="15f3e-201">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="15f3e-202">Nel campo Nome digitare "MessageIdentification".</span><span class="sxs-lookup"><span data-stu-id="15f3e-202">In the Name field, type 'MessageIdentification'.</span></span>
    * <span data-ttu-id="15f3e-203">MessageIdentification</span><span class="sxs-lookup"><span data-stu-id="15f3e-203">MessageIdentification</span></span>  
9. <span data-ttu-id="15f3e-204">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="15f3e-204">Click Add.</span></span>
10. <span data-ttu-id="15f3e-205">Nel campo Descrizione immettere 'Riferimento punto a punto assegnato dalla parte che impartisce le istruzioni e inviato alla parte successiva per identificare un messaggio'.</span><span class="sxs-lookup"><span data-stu-id="15f3e-205">In the Description field, enter 'The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.'.</span></span>
    * <span data-ttu-id="15f3e-206">Riferimento punto a punto assegnato dalla parte che impartisce le istruzioni e inviato alla parte successiva per identificare un messaggio.</span><span class="sxs-lookup"><span data-stu-id="15f3e-206">The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.</span></span>  
11. <span data-ttu-id="15f3e-207">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="15f3e-207">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="15f3e-208">Nel campo Nome digitare "ProcessingDateTime".</span><span class="sxs-lookup"><span data-stu-id="15f3e-208">In the Name field, type 'ProcessingDateTime'.</span></span>
    * <span data-ttu-id="15f3e-209">ProcessingDateTime</span><span class="sxs-lookup"><span data-stu-id="15f3e-209">ProcessingDateTime</span></span>  
13. <span data-ttu-id="15f3e-210">Nel campo Tipo di articolo selezionare "DateTime".</span><span class="sxs-lookup"><span data-stu-id="15f3e-210">In the Item type field, select 'DateTime'.</span></span>
14. <span data-ttu-id="15f3e-211">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="15f3e-211">Click Add.</span></span>
15. <span data-ttu-id="15f3e-212">Nel campo Descrizione immettere 'Data e ora di creazione del messaggio di pagamento.'.</span><span class="sxs-lookup"><span data-stu-id="15f3e-212">In the Description field, enter 'Date and time at which the payment message was created.'.</span></span>
    * <span data-ttu-id="15f3e-213">Data e ora di creazione del messaggio di pagamento.</span><span class="sxs-lookup"><span data-stu-id="15f3e-213">Date and time at which the payment message was created.</span></span>  
16. <span data-ttu-id="15f3e-214">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="15f3e-214">Click New to open the drop dialog.</span></span>
    * <span data-ttu-id="15f3e-215">Definire la struttura della transazione di pagamento per il modello.</span><span class="sxs-lookup"><span data-stu-id="15f3e-215">Define the payment transaction structure for this model.</span></span>  
17. <span data-ttu-id="15f3e-216">Nel campo Nome digitare "Pagamenti".</span><span class="sxs-lookup"><span data-stu-id="15f3e-216">In the Name field, type 'Payments'.</span></span>
    * <span data-ttu-id="15f3e-217">Pagamenti</span><span class="sxs-lookup"><span data-stu-id="15f3e-217">Payments</span></span>  
18. <span data-ttu-id="15f3e-218">Nel campo Tipo di articolo selezionare "Elenco di record".</span><span class="sxs-lookup"><span data-stu-id="15f3e-218">In the Item type field, select 'Record list'.</span></span>
19. <span data-ttu-id="15f3e-219">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="15f3e-219">Click Add.</span></span>
20. <span data-ttu-id="15f3e-220">Nel campo Descrizione immettere "Righe pagamento del messaggio corrente".</span><span class="sxs-lookup"><span data-stu-id="15f3e-220">In the Description field, enter 'Payment lines of the current message'.</span></span>
    * <span data-ttu-id="15f3e-221">Righe pagamento del messaggio corrente</span><span class="sxs-lookup"><span data-stu-id="15f3e-221">Payment lines of the current message</span></span>  
21. <span data-ttu-id="15f3e-222">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="15f3e-222">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="15f3e-223">Nel campo Nome digitare "Creditore".</span><span class="sxs-lookup"><span data-stu-id="15f3e-223">In the Name field, type 'Creditor'.</span></span>
    * <span data-ttu-id="15f3e-224">Creditore</span><span class="sxs-lookup"><span data-stu-id="15f3e-224">Creditor</span></span>  
23. <span data-ttu-id="15f3e-225">Nel campo Tipo di articolo selezionare "Record".</span><span class="sxs-lookup"><span data-stu-id="15f3e-225">In the Item type field, select 'Record'.</span></span>
24. <span data-ttu-id="15f3e-226">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="15f3e-226">Click Add.</span></span>
25. <span data-ttu-id="15f3e-227">Nel campo Descrizione immettere 'Parte a cui è dovuta una somma di denaro.'.</span><span class="sxs-lookup"><span data-stu-id="15f3e-227">In the Description field, enter 'Party to which an amount of money is due.'.</span></span>
    * <span data-ttu-id="15f3e-228">Parte a cui è dovuta una somma di denaro.</span><span class="sxs-lookup"><span data-stu-id="15f3e-228">Party to which an amount of money is due.</span></span>  
26. <span data-ttu-id="15f3e-229">Fare clic su Cambia riferimento articolo.</span><span class="sxs-lookup"><span data-stu-id="15f3e-229">Click Switch item reference.</span></span>
27. <span data-ttu-id="15f3e-230">Digitare 'Party' nel campo Trova.</span><span class="sxs-lookup"><span data-stu-id="15f3e-230">In the Find field, type 'Party'.</span></span>
    * <span data-ttu-id="15f3e-231">Parte</span><span class="sxs-lookup"><span data-stu-id="15f3e-231">Party</span></span>  
28. <span data-ttu-id="15f3e-232">Fare clic su Trova successivo.</span><span class="sxs-lookup"><span data-stu-id="15f3e-232">Click Find next.</span></span>
29. <span data-ttu-id="15f3e-233">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="15f3e-233">Click OK.</span></span>
30. <span data-ttu-id="15f3e-234">Nel campo Trova digitare 'Pagamenti'.</span><span class="sxs-lookup"><span data-stu-id="15f3e-234">In the Find field, type 'Payments'.</span></span>
    * <span data-ttu-id="15f3e-235">Pagamenti</span><span class="sxs-lookup"><span data-stu-id="15f3e-235">Payments</span></span>  
31. <span data-ttu-id="15f3e-236">Fare clic su Trova successivo.</span><span class="sxs-lookup"><span data-stu-id="15f3e-236">Click Find next.</span></span>
32. <span data-ttu-id="15f3e-237">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="15f3e-237">Click New to open the drop dialog.</span></span>
33. <span data-ttu-id="15f3e-238">Nel campo nome digitare "Debitore".</span><span class="sxs-lookup"><span data-stu-id="15f3e-238">In the Name field, type 'Debtor'.</span></span>
    * <span data-ttu-id="15f3e-239">Debitore</span><span class="sxs-lookup"><span data-stu-id="15f3e-239">Debtor</span></span>  
34. <span data-ttu-id="15f3e-240">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="15f3e-240">Click Add.</span></span>
35. <span data-ttu-id="15f3e-241">Nel campo Descrizione immettere 'Parte che deve una somma di denaro al creditore (finale).'.</span><span class="sxs-lookup"><span data-stu-id="15f3e-241">In the Description field, enter 'Party that owes an amount of money to the (ultimate) creditor.'.</span></span>
    * <span data-ttu-id="15f3e-242">Parte che deve una somma di denaro al creditore (finale).</span><span class="sxs-lookup"><span data-stu-id="15f3e-242">Party that owes an amount of money to the (ultimate) creditor.</span></span>  
36. <span data-ttu-id="15f3e-243">Fare clic su Cambia riferimento articolo.</span><span class="sxs-lookup"><span data-stu-id="15f3e-243">Click Switch item reference.</span></span>
37. <span data-ttu-id="15f3e-244">Digitare 'Party' nel campo Trova.</span><span class="sxs-lookup"><span data-stu-id="15f3e-244">In the Find field, type 'Party'.</span></span>
    * <span data-ttu-id="15f3e-245">Parte</span><span class="sxs-lookup"><span data-stu-id="15f3e-245">Party</span></span>  
38. <span data-ttu-id="15f3e-246">Fare clic su Trova successivo.</span><span class="sxs-lookup"><span data-stu-id="15f3e-246">Click Find next.</span></span>
39. <span data-ttu-id="15f3e-247">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="15f3e-247">Click OK.</span></span>
40. <span data-ttu-id="15f3e-248">Fare clic su Trova successivo.</span><span class="sxs-lookup"><span data-stu-id="15f3e-248">Click Find next.</span></span>
41. <span data-ttu-id="15f3e-249">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="15f3e-249">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="15f3e-250">Nel campo Nome digitare "Descrizione".</span><span class="sxs-lookup"><span data-stu-id="15f3e-250">In the Name field, type 'Description'.</span></span>
    * <span data-ttu-id="15f3e-251">descrizione</span><span class="sxs-lookup"><span data-stu-id="15f3e-251">Description</span></span>  
43. <span data-ttu-id="15f3e-252">Nel campo Tipo di articolo selezionare "Stringa".</span><span class="sxs-lookup"><span data-stu-id="15f3e-252">In the Item type field, select 'String'.</span></span>
44. <span data-ttu-id="15f3e-253">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="15f3e-253">Click Add.</span></span>
45. <span data-ttu-id="15f3e-254">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="15f3e-254">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="15f3e-255">Nel campo Nome digitare "Valuta".</span><span class="sxs-lookup"><span data-stu-id="15f3e-255">In the Name field, type 'Currency'.</span></span>
    * <span data-ttu-id="15f3e-256">Valuta</span><span class="sxs-lookup"><span data-stu-id="15f3e-256">Currency</span></span>  
47. <span data-ttu-id="15f3e-257">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="15f3e-257">Click Add.</span></span>
48. <span data-ttu-id="15f3e-258">Nel campo Descrizione immettere 'Codice valuta'.</span><span class="sxs-lookup"><span data-stu-id="15f3e-258">In the Description field, enter 'Currency code'.</span></span>
    * <span data-ttu-id="15f3e-259">Codice valuta</span><span class="sxs-lookup"><span data-stu-id="15f3e-259">Currency code</span></span>  
49. <span data-ttu-id="15f3e-260">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="15f3e-260">Click New to open the drop dialog.</span></span>
50. <span data-ttu-id="15f3e-261">Nel campo Nome digitare "TransactionDate".</span><span class="sxs-lookup"><span data-stu-id="15f3e-261">In the Name field, type 'TransactionDate'.</span></span>
    * <span data-ttu-id="15f3e-262">TransactionDate</span><span class="sxs-lookup"><span data-stu-id="15f3e-262">TransactionDate</span></span>  
51. <span data-ttu-id="15f3e-263">Nel campo Tipo di articolo selezionare "Data".</span><span class="sxs-lookup"><span data-stu-id="15f3e-263">In the Item type field, select 'Date'.</span></span>
52. <span data-ttu-id="15f3e-264">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="15f3e-264">Click Add.</span></span>
53. <span data-ttu-id="15f3e-265">Nel campo Descrizione immettere 'Data della transazione'.</span><span class="sxs-lookup"><span data-stu-id="15f3e-265">In the Description field, enter 'Transaction date'.</span></span>
    * <span data-ttu-id="15f3e-266">Data della transazione</span><span class="sxs-lookup"><span data-stu-id="15f3e-266">Transaction date</span></span>  
54. <span data-ttu-id="15f3e-267">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="15f3e-267">Click New to open the drop dialog.</span></span>
55. <span data-ttu-id="15f3e-268">Nel campo Nome digitare "InstructedAmount".</span><span class="sxs-lookup"><span data-stu-id="15f3e-268">In the Name field, type 'InstructedAmount'.</span></span>
    * <span data-ttu-id="15f3e-269">InstructedAmount</span><span class="sxs-lookup"><span data-stu-id="15f3e-269">InstructedAmount</span></span>  
56. <span data-ttu-id="15f3e-270">Nel campo Tipo di articolo selezionare "Reale".</span><span class="sxs-lookup"><span data-stu-id="15f3e-270">In the Item type field, select 'Real'.</span></span>
57. <span data-ttu-id="15f3e-271">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="15f3e-271">Click Add.</span></span>
58. <span data-ttu-id="15f3e-272">Nel campo Descrizione immettere 'Somma di denaro da trasferire tra il debitore e il creditore al lordo delle detrazione di oneri.</span><span class="sxs-lookup"><span data-stu-id="15f3e-272">In the Description field, enter 'The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="15f3e-273">L'importo deve essere espresso nella valuta indicata dalla parte che inizia la transazione".</span><span class="sxs-lookup"><span data-stu-id="15f3e-273">The amount should be expressed in the currency as ordered by the initiating party.'.</span></span>
    * <span data-ttu-id="15f3e-274">Somma di denaro da trasferire tra il debitore e il creditore al lordo delle detrazione di oneri.</span><span class="sxs-lookup"><span data-stu-id="15f3e-274">The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="15f3e-275">L'importo deve essere espresso nella valuta indicata dalla parte che inizia la transazione.</span><span class="sxs-lookup"><span data-stu-id="15f3e-275">The amount should be expressed in the currency as ordered by the initiating party.</span></span>  
59. <span data-ttu-id="15f3e-276">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="15f3e-276">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="15f3e-277">Nel campo Nome digitare "End2EndID".</span><span class="sxs-lookup"><span data-stu-id="15f3e-277">In the Name field, type 'End2EndID'.</span></span>
    * <span data-ttu-id="15f3e-278">End2EndID</span><span class="sxs-lookup"><span data-stu-id="15f3e-278">End2EndID</span></span>  
61. <span data-ttu-id="15f3e-279">Nel campo Tipo di articolo selezionare "Stringa".</span><span class="sxs-lookup"><span data-stu-id="15f3e-279">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="15f3e-280">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="15f3e-280">Click Add.</span></span>
63. <span data-ttu-id="15f3e-281">Nel campo Descrizione immettere 'Identificazione univoca assegnata dalla parte che inizia la transazione.</span><span class="sxs-lookup"><span data-stu-id="15f3e-281">In the Description field, enter 'The unique identification assigned by the initiating party.</span></span> <span data-ttu-id="15f3e-282">L'identificazione viene passata senza modifiche lungo l'intera catena end-to-end".</span><span class="sxs-lookup"><span data-stu-id="15f3e-282">This identification is passed on, unchanged, throughout the entire end-to-end chain.'.</span></span>
    * <span data-ttu-id="15f3e-283">Identificazione univoca assegnata dalla parte che inizia la transazione.</span><span class="sxs-lookup"><span data-stu-id="15f3e-283">The unique identification assigned by the initiating party.</span></span> <span data-ttu-id="15f3e-284">L'identificazione viene passata senza modifiche lungo l'intera catena end-to-end.</span><span class="sxs-lookup"><span data-stu-id="15f3e-284">This identification is passed on, unchanged, throughout the entire end-to-end chain.</span></span>  
64. <span data-ttu-id="15f3e-285">Nel campo Nome digitare "PaymentModel".</span><span class="sxs-lookup"><span data-stu-id="15f3e-285">In the Name field, type 'PaymentModel'.</span></span>
    * <span data-ttu-id="15f3e-286">Il nome PaymentModel è in linea con le interfacce predefinite delle forme di pagamento.</span><span class="sxs-lookup"><span data-stu-id="15f3e-286">The PaymentModel name aligns with predefined interfaces of payment forms.</span></span>  
65. <span data-ttu-id="15f3e-287">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="15f3e-287">Click Save.</span></span>
66. <span data-ttu-id="15f3e-288">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="15f3e-288">Close the page.</span></span>


