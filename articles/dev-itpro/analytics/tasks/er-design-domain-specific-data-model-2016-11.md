--- 
title: RE Progettare il modello dati specifico di dominio
description: "I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare una nuova configurazione per la creazione di report elettronici che contiene un modello dati per i documenti di pagamento elettronico."
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERDataContainerDescriptorReferenceSwitchDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 0debb7276c4f3e41c2e85ce6bc63b8df5bc159f8
ms.contentlocale: it-it
ms.lasthandoff: 10/16/2018

---
# <a name="er-design-domain-specific-data-model"></a><span data-ttu-id="9d7c2-103">RE Progettare il modello dati specifico di dominio</span><span class="sxs-lookup"><span data-stu-id="9d7c2-103">ER Design domain specific data model</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9d7c2-104">I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare una nuova configurazione per la creazione di report elettronici che contiene un modello dati per i documenti di pagamento elettronico.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="9d7c2-105">Questo modello dati verrà utilizzato successivamente come origine dati quando si crea il formato dei documenti di pagamento.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-105">This data model will later be used as a data source when you create the format of the payment documents.</span></span>



<span data-ttu-id="9d7c2-106">In questo esempio verrà creata una configurazione per la società di esempio Litware, Inc. Queste operazioni possono essere eseguite in qualsiasi società perché le configurazioni per la creazione di report elettronici sono condivise tra tutte le società.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="9d7c2-107">Per completare questi passaggi, è necessario completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-107">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>

1. <span data-ttu-id="9d7c2-108">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="9d7c2-109">Selezionare il provider di configurazione per la società di esempio Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-109">Select the configuration provider for sample company, ‘Litware, Inc.’</span></span> <span data-ttu-id="9d7c2-110">Se il provider di configurazione non viene visualizzato, è necessario innanzitutto completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-110">If you don’t see this configuration provider, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>  
2. <span data-ttu-id="9d7c2-111">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-111">Click Reporting configurations.</span></span>
    * <span data-ttu-id="9d7c2-112">Verrà creata una configurazione che contiene un modello dati per i documenti di pagamento elettronico.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-112">You will create a configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="9d7c2-113">Questo modello dati verrà utilizzato successivamente come origine dati quando si crea il formato dei documenti di pagamento.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-113">This data model will be used later as a data source when you create the format for the payment documents.</span></span>  

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="9d7c2-114">Crea una nuova configurazione di modello dati</span><span class="sxs-lookup"><span data-stu-id="9d7c2-114">Create a new data model configuration</span></span>
1. <span data-ttu-id="9d7c2-115">Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .</span><span class="sxs-lookup"><span data-stu-id="9d7c2-115">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="9d7c2-116">Nel campo Nome digitare "Pagamenti (modello semplificato)".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-116">In the Name field, type 'Payments (simplified model)'.</span></span>
    * <span data-ttu-id="9d7c2-117">Pagamenti (modello semplificato)</span><span class="sxs-lookup"><span data-stu-id="9d7c2-117">Payments (simplified model)</span></span>  
3. <span data-ttu-id="9d7c2-118">Nel campo Descrizione digitare "Configurazione modello di pagamento".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-118">In the Description field, type 'Payment model configuration'.</span></span>
    * <span data-ttu-id="9d7c2-119">Configurazione modello di pagamento</span><span class="sxs-lookup"><span data-stu-id="9d7c2-119">Payment model configuration</span></span>  
    * <span data-ttu-id="9d7c2-120">Il provider di configurazione attiva viene inserito automaticamente in questo punto.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-120">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="9d7c2-121">Tale provider potrà gestire la configurazione.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-121">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="9d7c2-122">Altri provider possono utilizzare la configurazione, ma non potranno gestirla.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-122">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
4. <span data-ttu-id="9d7c2-123">Fare clic sul pulsante "Crea configurazione" per completare l'attività di creazione della configurazione</span><span class="sxs-lookup"><span data-stu-id="9d7c2-123">Click ‘Create configuration’ button to complete the configuration creation task</span></span>

## <a name="create-a-data-model"></a><span data-ttu-id="9d7c2-124">Creare un modello dati</span><span class="sxs-lookup"><span data-stu-id="9d7c2-124">Create a data model</span></span>
    * <span data-ttu-id="9d7c2-125">Si sta creando un nuovo modello dati per la configurazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-125">You're creating a new data model for the selected configuration.</span></span> <span data-ttu-id="9d7c2-126">Questa versione di configurazione avrà lo stato di bozza.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-126">This configuration version will have a status of Draft.</span></span>  
1. <span data-ttu-id="9d7c2-127">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-127">Click Designer.</span></span>

## <a name="define-the-structure-of-a-party-participating-in-a-payment-process"></a><span data-ttu-id="9d7c2-128">Definire la struttura di una parte che partecipa a un processo di pagamento</span><span class="sxs-lookup"><span data-stu-id="9d7c2-128">Define the structure of a party participating in a payment process</span></span>
1. <span data-ttu-id="9d7c2-129">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-129">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="9d7c2-130">Digitare 'Party' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-130">In the Name field, type 'Party'.</span></span>
    * <span data-ttu-id="9d7c2-131">Parte</span><span class="sxs-lookup"><span data-stu-id="9d7c2-131">Party</span></span>  
3. <span data-ttu-id="9d7c2-132">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-132">Click Add.</span></span>
4. <span data-ttu-id="9d7c2-133">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-133">Click New to open the drop dialog.</span></span>
5. <span data-ttu-id="9d7c2-134">Nel campo Nome digitare "Nome".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-134">In the Name field, type 'Name'.</span></span>
    * <span data-ttu-id="9d7c2-135">Nome</span><span class="sxs-lookup"><span data-stu-id="9d7c2-135">Name</span></span>  
6. <span data-ttu-id="9d7c2-136">Nel campo Tipo di articolo selezionare "Stringa".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-136">In the Item type field, select 'String'.</span></span>
7. <span data-ttu-id="9d7c2-137">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-137">Click Add.</span></span>
8. <span data-ttu-id="9d7c2-138">Digitare 'Party' nel campo Trova.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-138">In the Find field, type 'Party'.</span></span>
    * <span data-ttu-id="9d7c2-139">Parte</span><span class="sxs-lookup"><span data-stu-id="9d7c2-139">Party</span></span>  
9. <span data-ttu-id="9d7c2-140">Fare clic su Trova precedente.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-140">Click Find previous.</span></span>

## <a name="define-the-bank-structure-for-this-model"></a><span data-ttu-id="9d7c2-141">Definire la struttura della banca per il modello</span><span class="sxs-lookup"><span data-stu-id="9d7c2-141">Define the bank structure for this model</span></span>
1. <span data-ttu-id="9d7c2-142">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-142">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="9d7c2-143">Nel campo Nome digitare "Agente".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-143">In the Name field, type 'Agent'.</span></span>
    * <span data-ttu-id="9d7c2-144">Agente</span><span class="sxs-lookup"><span data-stu-id="9d7c2-144">Agent</span></span>  
3. <span data-ttu-id="9d7c2-145">Nel campo Tipo di articolo selezionare "Record".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-145">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="9d7c2-146">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-146">Click Add.</span></span>
5. <span data-ttu-id="9d7c2-147">Nel campo Descrizione immettere 'Istituto finanziario, ad esempio una banca, responsabile di un conto per la parte (debitore/creditore).'.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-147">In the Description field, enter 'Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).'.</span></span>
    * <span data-ttu-id="9d7c2-148">Istituto finanziario, ad esempio una banca, responsabile di un conto per la parte (debitore/creditore).</span><span class="sxs-lookup"><span data-stu-id="9d7c2-148">Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).</span></span>  
6. <span data-ttu-id="9d7c2-149">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-149">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="9d7c2-150">Nel campo Nome digitare "Nome".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-150">In the Name field, type 'Name'.</span></span>
    * <span data-ttu-id="9d7c2-151">Nome</span><span class="sxs-lookup"><span data-stu-id="9d7c2-151">Name</span></span>  
8. <span data-ttu-id="9d7c2-152">Nel campo Tipo di articolo selezionare "Stringa".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-152">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="9d7c2-153">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-153">Click Add.</span></span>
10. <span data-ttu-id="9d7c2-154">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-154">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="9d7c2-155">Nel campo Nome digitare "SWIFT".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-155">In the Name field, type 'SWIFT'.</span></span>
    * <span data-ttu-id="9d7c2-156">SWIFT</span><span class="sxs-lookup"><span data-stu-id="9d7c2-156">SWIFT</span></span>  
12. <span data-ttu-id="9d7c2-157">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-157">Click Add.</span></span>
13. <span data-ttu-id="9d7c2-158">Nel campo Descrizione immettere 'Codice di identificazione bancario'.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-158">In the Description field, enter 'Bank identification code'.</span></span>
    * <span data-ttu-id="9d7c2-159">Codice di identificazione bancario</span><span class="sxs-lookup"><span data-stu-id="9d7c2-159">Bank identification code</span></span>  
14. <span data-ttu-id="9d7c2-160">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-160">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="9d7c2-161">Nel campo Nome digitare "RoutingNumber".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-161">In the Name field, type 'RoutingNumber'.</span></span>
    * <span data-ttu-id="9d7c2-162">RoutingNumber</span><span class="sxs-lookup"><span data-stu-id="9d7c2-162">RoutingNumber</span></span>  
16. <span data-ttu-id="9d7c2-163">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-163">Click Add.</span></span>
17. <span data-ttu-id="9d7c2-164">Nel campo Descrizione immettere 'Numero di registrazione'.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-164">In the Description field, enter 'Routing number'.</span></span>
    * <span data-ttu-id="9d7c2-165">Numero di registrazione</span><span class="sxs-lookup"><span data-stu-id="9d7c2-165">Routing number</span></span>  
18. <span data-ttu-id="9d7c2-166">Fare clic su Trova precedente.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-166">Click Find previous.</span></span>

## <a name="define-the-bank-account-structure-for-this-model"></a><span data-ttu-id="9d7c2-167">Definire la struttura del conto bancario per il modello</span><span class="sxs-lookup"><span data-stu-id="9d7c2-167">Define the bank account structure for this model</span></span>
1. <span data-ttu-id="9d7c2-168">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-168">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="9d7c2-169">Nel campo Nome digitare "Conto".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-169">In the Name field, type 'Account'.</span></span>
    * <span data-ttu-id="9d7c2-170">Conto</span><span class="sxs-lookup"><span data-stu-id="9d7c2-170">Account</span></span>  
3. <span data-ttu-id="9d7c2-171">Nel campo Tipo di articolo selezionare "Record".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-171">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="9d7c2-172">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-172">Click Add.</span></span>
5. <span data-ttu-id="9d7c2-173">Nel campo Descrizione, immettere 'Identificazione di un conto di una parte di un istituto finanziario, ad esempio una banca.'.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-173">In the Description field, enter 'Identification of an account of a party in a financial institution (for instance, a bank).'.</span></span>
    * <span data-ttu-id="9d7c2-174">Identificazione di un conto di una parte di un istituto finanziario, ad esempio una banca.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-174">Identification of an account of a party in a financial institution (for instance, a bank).</span></span>  
6. <span data-ttu-id="9d7c2-175">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-175">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="9d7c2-176">Nel campo Nome digitare "Valuta".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-176">In the Name field, type 'Currency'.</span></span>
    * <span data-ttu-id="9d7c2-177">Valuta</span><span class="sxs-lookup"><span data-stu-id="9d7c2-177">Currency</span></span>  
8. <span data-ttu-id="9d7c2-178">Nel campo Tipo di articolo selezionare "Stringa".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-178">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="9d7c2-179">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-179">Click Add.</span></span>
10. <span data-ttu-id="9d7c2-180">Nel campo Descrizione immettere 'Codice valuta'.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-180">In the Description field, enter 'Currency code'.</span></span>
    * <span data-ttu-id="9d7c2-181">Codice valuta</span><span class="sxs-lookup"><span data-stu-id="9d7c2-181">Currency code</span></span>  
11. <span data-ttu-id="9d7c2-182">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-182">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="9d7c2-183">Nel campo Nome digitare "Numero".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-183">In the Name field, type 'Number'.</span></span>
    * <span data-ttu-id="9d7c2-184">Numero</span><span class="sxs-lookup"><span data-stu-id="9d7c2-184">Number</span></span>  
13. <span data-ttu-id="9d7c2-185">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-185">Click Add.</span></span>
14. <span data-ttu-id="9d7c2-186">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-186">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="9d7c2-187">Nel campo nome digitare "IBAN".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-187">In the Name field, type 'IBAN'.</span></span>
    * <span data-ttu-id="9d7c2-188">IBAN</span><span class="sxs-lookup"><span data-stu-id="9d7c2-188">IBAN</span></span>  
16. <span data-ttu-id="9d7c2-189">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-189">Click Add.</span></span>
17. <span data-ttu-id="9d7c2-190">Nel campo Descrizione immettere 'International Bank Account Number (numero di conto bancario internazionale)'.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-190">In the Description field, enter 'International bank account number'.</span></span>
    * <span data-ttu-id="9d7c2-191">International Bank Account Number (numero di conto bancario internazionale)</span><span class="sxs-lookup"><span data-stu-id="9d7c2-191">International bank account number</span></span>  

## <a name="define-the-payment-message-structure-for-credit-transfer-payment-type"></a><span data-ttu-id="9d7c2-192">Definire la struttura del messaggio di pagamento per il tipo di pagamento con bonifico</span><span class="sxs-lookup"><span data-stu-id="9d7c2-192">Define the payment message structure for credit transfer payment type</span></span>
1. <span data-ttu-id="9d7c2-193">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-193">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="9d7c2-194">Nel campo Nuovo nodo come immettere 'Radice modello'.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-194">In the New node as a field, enter 'Model root'.</span></span>
3. <span data-ttu-id="9d7c2-195">Nel campo Nome digitare "CustomerCreditTransferInitiation".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-195">In the Name field, type 'CustomerCreditTransferInitiation'.</span></span>
    * <span data-ttu-id="9d7c2-196">CustomerCreditTransferInitiation</span><span class="sxs-lookup"><span data-stu-id="9d7c2-196">CustomerCreditTransferInitiation</span></span>  
4. <span data-ttu-id="9d7c2-197">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-197">Click Add.</span></span>
5. <span data-ttu-id="9d7c2-198">Nel campo Trova digitare 'CustomerCreditTransferInitiation'.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-198">In the Find field, type 'CustomerCreditTransferInitiation'.</span></span>
    * <span data-ttu-id="9d7c2-199">CustomerCreditTransferInitiation</span><span class="sxs-lookup"><span data-stu-id="9d7c2-199">CustomerCreditTransferInitiation</span></span>  
6. <span data-ttu-id="9d7c2-200">Fare clic su Trova precedente.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-200">Click Find previous.</span></span>
7. <span data-ttu-id="9d7c2-201">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-201">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="9d7c2-202">Nel campo Nome digitare "MessageIdentification".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-202">In the Name field, type 'MessageIdentification'.</span></span>
    * <span data-ttu-id="9d7c2-203">MessageIdentification</span><span class="sxs-lookup"><span data-stu-id="9d7c2-203">MessageIdentification</span></span>  
9. <span data-ttu-id="9d7c2-204">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-204">Click Add.</span></span>
10. <span data-ttu-id="9d7c2-205">Nel campo Descrizione immettere 'Riferimento punto a punto assegnato dalla parte che impartisce le istruzioni e inviato alla parte successiva per identificare un messaggio'.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-205">In the Description field, enter 'The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.'.</span></span>
    * <span data-ttu-id="9d7c2-206">Riferimento punto a punto assegnato dalla parte che impartisce le istruzioni e inviato alla parte successiva per identificare un messaggio.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-206">The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.</span></span>  
11. <span data-ttu-id="9d7c2-207">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-207">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="9d7c2-208">Nel campo Nome digitare "ProcessingDateTime".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-208">In the Name field, type 'ProcessingDateTime'.</span></span>
    * <span data-ttu-id="9d7c2-209">ProcessingDateTime</span><span class="sxs-lookup"><span data-stu-id="9d7c2-209">ProcessingDateTime</span></span>  
13. <span data-ttu-id="9d7c2-210">Nel campo Tipo di articolo selezionare "DateTime".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-210">In the Item type field, select 'DateTime'.</span></span>
14. <span data-ttu-id="9d7c2-211">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-211">Click Add.</span></span>
15. <span data-ttu-id="9d7c2-212">Nel campo Descrizione immettere 'Data e ora di creazione del messaggio di pagamento.'.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-212">In the Description field, enter 'Date and time at which the payment message was created.'.</span></span>
    * <span data-ttu-id="9d7c2-213">Data e ora di creazione del messaggio di pagamento.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-213">Date and time at which the payment message was created.</span></span>  
16. <span data-ttu-id="9d7c2-214">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-214">Click New to open the drop dialog.</span></span>
    * <span data-ttu-id="9d7c2-215">Definire la struttura della transazione di pagamento per il modello.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-215">Define the payment transaction structure for this model.</span></span>  
17. <span data-ttu-id="9d7c2-216">Nel campo Nome digitare "Pagamenti".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-216">In the Name field, type 'Payments'.</span></span>
    * <span data-ttu-id="9d7c2-217">Pagamenti</span><span class="sxs-lookup"><span data-stu-id="9d7c2-217">Payments</span></span>  
18. <span data-ttu-id="9d7c2-218">Nel campo Tipo di articolo selezionare "Elenco di record".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-218">In the Item type field, select 'Record list'.</span></span>
19. <span data-ttu-id="9d7c2-219">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-219">Click Add.</span></span>
20. <span data-ttu-id="9d7c2-220">Nel campo Descrizione immettere "Righe pagamento del messaggio corrente".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-220">In the Description field, enter 'Payment lines of the current message'.</span></span>
    * <span data-ttu-id="9d7c2-221">Righe pagamento del messaggio corrente</span><span class="sxs-lookup"><span data-stu-id="9d7c2-221">Payment lines of the current message</span></span>  
21. <span data-ttu-id="9d7c2-222">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-222">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="9d7c2-223">Nel campo Nome digitare "Creditore".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-223">In the Name field, type 'Creditor'.</span></span>
    * <span data-ttu-id="9d7c2-224">Creditore</span><span class="sxs-lookup"><span data-stu-id="9d7c2-224">Creditor</span></span>  
23. <span data-ttu-id="9d7c2-225">Nel campo Tipo di articolo selezionare "Record".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-225">In the Item type field, select 'Record'.</span></span>
24. <span data-ttu-id="9d7c2-226">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-226">Click Add.</span></span>
25. <span data-ttu-id="9d7c2-227">Nel campo Descrizione immettere 'Parte a cui è dovuta una somma di denaro.'.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-227">In the Description field, enter 'Party to which an amount of money is due.'.</span></span>
    * <span data-ttu-id="9d7c2-228">Parte a cui è dovuta una somma di denaro.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-228">Party to which an amount of money is due.</span></span>  
26. <span data-ttu-id="9d7c2-229">Fare clic su Cambia riferimento articolo.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-229">Click Switch item reference.</span></span>
27. <span data-ttu-id="9d7c2-230">Digitare 'Party' nel campo Trova.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-230">In the Find field, type 'Party'.</span></span>
    * <span data-ttu-id="9d7c2-231">Parte</span><span class="sxs-lookup"><span data-stu-id="9d7c2-231">Party</span></span>  
28. <span data-ttu-id="9d7c2-232">Fare clic su Trova successivo.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-232">Click Find next.</span></span>
29. <span data-ttu-id="9d7c2-233">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-233">Click OK.</span></span>
30. <span data-ttu-id="9d7c2-234">Nel campo Trova digitare 'Pagamenti'.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-234">In the Find field, type 'Payments'.</span></span>
    * <span data-ttu-id="9d7c2-235">Pagamenti</span><span class="sxs-lookup"><span data-stu-id="9d7c2-235">Payments</span></span>  
31. <span data-ttu-id="9d7c2-236">Fare clic su Trova successivo.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-236">Click Find next.</span></span>
32. <span data-ttu-id="9d7c2-237">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-237">Click New to open the drop dialog.</span></span>
33. <span data-ttu-id="9d7c2-238">Nel campo nome digitare "Debitore".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-238">In the Name field, type 'Debtor'.</span></span>
    * <span data-ttu-id="9d7c2-239">Debitore</span><span class="sxs-lookup"><span data-stu-id="9d7c2-239">Debtor</span></span>  
34. <span data-ttu-id="9d7c2-240">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-240">Click Add.</span></span>
35. <span data-ttu-id="9d7c2-241">Nel campo Descrizione immettere 'Parte che deve una somma di denaro al creditore (finale).'.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-241">In the Description field, enter 'Party that owes an amount of money to the (ultimate) creditor.'.</span></span>
    * <span data-ttu-id="9d7c2-242">Parte che deve una somma di denaro al creditore (finale).</span><span class="sxs-lookup"><span data-stu-id="9d7c2-242">Party that owes an amount of money to the (ultimate) creditor.</span></span>  
36. <span data-ttu-id="9d7c2-243">Fare clic su Cambia riferimento articolo.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-243">Click Switch item reference.</span></span>
37. <span data-ttu-id="9d7c2-244">Digitare 'Party' nel campo Trova.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-244">In the Find field, type 'Party'.</span></span>
    * <span data-ttu-id="9d7c2-245">Parte</span><span class="sxs-lookup"><span data-stu-id="9d7c2-245">Party</span></span>  
38. <span data-ttu-id="9d7c2-246">Fare clic su Trova successivo.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-246">Click Find next.</span></span>
39. <span data-ttu-id="9d7c2-247">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-247">Click OK.</span></span>
40. <span data-ttu-id="9d7c2-248">Fare clic su Trova successivo.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-248">Click Find next.</span></span>
41. <span data-ttu-id="9d7c2-249">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-249">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="9d7c2-250">Nel campo Nome digitare "Descrizione".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-250">In the Name field, type 'Description'.</span></span>
    * <span data-ttu-id="9d7c2-251">descrizione</span><span class="sxs-lookup"><span data-stu-id="9d7c2-251">Description</span></span>  
43. <span data-ttu-id="9d7c2-252">Nel campo Tipo di articolo selezionare "Stringa".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-252">In the Item type field, select 'String'.</span></span>
44. <span data-ttu-id="9d7c2-253">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-253">Click Add.</span></span>
45. <span data-ttu-id="9d7c2-254">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-254">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="9d7c2-255">Nel campo Nome digitare "Valuta".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-255">In the Name field, type 'Currency'.</span></span>
    * <span data-ttu-id="9d7c2-256">Valuta</span><span class="sxs-lookup"><span data-stu-id="9d7c2-256">Currency</span></span>  
47. <span data-ttu-id="9d7c2-257">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-257">Click Add.</span></span>
48. <span data-ttu-id="9d7c2-258">Nel campo Descrizione immettere 'Codice valuta'.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-258">In the Description field, enter 'Currency code'.</span></span>
    * <span data-ttu-id="9d7c2-259">Codice valuta</span><span class="sxs-lookup"><span data-stu-id="9d7c2-259">Currency code</span></span>  
49. <span data-ttu-id="9d7c2-260">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-260">Click New to open the drop dialog.</span></span>
50. <span data-ttu-id="9d7c2-261">Nel campo Nome digitare "TransactionDate".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-261">In the Name field, type 'TransactionDate'.</span></span>
    * <span data-ttu-id="9d7c2-262">TransactionDate</span><span class="sxs-lookup"><span data-stu-id="9d7c2-262">TransactionDate</span></span>  
51. <span data-ttu-id="9d7c2-263">Nel campo Tipo di articolo selezionare "Data".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-263">In the Item type field, select 'Date'.</span></span>
52. <span data-ttu-id="9d7c2-264">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-264">Click Add.</span></span>
53. <span data-ttu-id="9d7c2-265">Nel campo Descrizione immettere 'Data della transazione'.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-265">In the Description field, enter 'Transaction date'.</span></span>
    * <span data-ttu-id="9d7c2-266">Data della transazione</span><span class="sxs-lookup"><span data-stu-id="9d7c2-266">Transaction date</span></span>  
54. <span data-ttu-id="9d7c2-267">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-267">Click New to open the drop dialog.</span></span>
55. <span data-ttu-id="9d7c2-268">Nel campo Nome digitare "InstructedAmount".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-268">In the Name field, type 'InstructedAmount'.</span></span>
    * <span data-ttu-id="9d7c2-269">InstructedAmount</span><span class="sxs-lookup"><span data-stu-id="9d7c2-269">InstructedAmount</span></span>  
56. <span data-ttu-id="9d7c2-270">Nel campo Tipo di articolo selezionare "Reale".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-270">In the Item type field, select 'Real'.</span></span>
57. <span data-ttu-id="9d7c2-271">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-271">Click Add.</span></span>
58. <span data-ttu-id="9d7c2-272">Nel campo Descrizione immettere 'Somma di denaro da trasferire tra il debitore e il creditore al lordo delle detrazione di oneri.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-272">In the Description field, enter 'The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="9d7c2-273">L'importo deve essere espresso nella valuta indicata dalla parte che inizia la transazione".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-273">The amount should be expressed in the currency as ordered by the initiating party.'.</span></span>
    * <span data-ttu-id="9d7c2-274">Somma di denaro da trasferire tra il debitore e il creditore al lordo delle detrazione di oneri.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-274">The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="9d7c2-275">L'importo deve essere espresso nella valuta indicata dalla parte che inizia la transazione.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-275">The amount should be expressed in the currency as ordered by the initiating party.</span></span>  
59. <span data-ttu-id="9d7c2-276">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-276">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="9d7c2-277">Nel campo Nome digitare "End2EndID".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-277">In the Name field, type 'End2EndID'.</span></span>
    * <span data-ttu-id="9d7c2-278">End2EndID</span><span class="sxs-lookup"><span data-stu-id="9d7c2-278">End2EndID</span></span>  
61. <span data-ttu-id="9d7c2-279">Nel campo Tipo di articolo selezionare "Stringa".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-279">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="9d7c2-280">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-280">Click Add.</span></span>
63. <span data-ttu-id="9d7c2-281">Nel campo Descrizione immettere 'Identificazione univoca assegnata dalla parte che inizia la transazione.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-281">In the Description field, enter 'The unique identification assigned by the initiating party.</span></span> <span data-ttu-id="9d7c2-282">L'identificazione viene passata senza modifiche lungo l'intera catena end-to-end".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-282">This identification is passed on, unchanged, throughout the entire end-to-end chain.'.</span></span>
    * <span data-ttu-id="9d7c2-283">Identificazione univoca assegnata dalla parte che inizia la transazione.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-283">The unique identification assigned by the initiating party.</span></span> <span data-ttu-id="9d7c2-284">L'identificazione viene passata senza modifiche lungo l'intera catena end-to-end.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-284">This identification is passed on, unchanged, throughout the entire end-to-end chain.</span></span>  
64. <span data-ttu-id="9d7c2-285">Nel campo Nome digitare "PaymentModel".</span><span class="sxs-lookup"><span data-stu-id="9d7c2-285">In the Name field, type 'PaymentModel'.</span></span>
    * <span data-ttu-id="9d7c2-286">Il nome PaymentModel è in linea con le interfacce predefinite delle forme di pagamento.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-286">The PaymentModel name aligns with predefined interfaces of payment forms.</span></span>  
65. <span data-ttu-id="9d7c2-287">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-287">Click Save.</span></span>
66. <span data-ttu-id="9d7c2-288">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-288">Close the page.</span></span>


