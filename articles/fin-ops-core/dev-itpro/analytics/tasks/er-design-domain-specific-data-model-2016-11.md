---
title: RE Progettare il modello dati specifico di dominio
description: Questo argomento descrive come creare una nuova configurazione di reporting elettronico (ER) che contiene un modello di dati per i documenti di pagamento elettronico.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERDataContainerDescriptorReferenceSwitchDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 284fad8b6646c35217789cc9936cbe9fe75a03d0
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567811"
---
# <a name="er-design-domain-specific-data-model"></a><span data-ttu-id="5089f-103">RE Progettare il modello dati specifico di dominio</span><span class="sxs-lookup"><span data-stu-id="5089f-103">ER Design domain specific data model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5089f-104">I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare una nuova configurazione per la creazione di report elettronici che contiene un modello dati per i documenti di pagamento elettronico.</span><span class="sxs-lookup"><span data-stu-id="5089f-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="5089f-105">Questo modello dati verrà utilizzato successivamente come origine dati quando si crea il formato dei documenti di pagamento.</span><span class="sxs-lookup"><span data-stu-id="5089f-105">This data model will later be used as a data source when you create the format of the payment documents.</span></span>

<span data-ttu-id="5089f-106">In questo esempio verrà creata una configurazione per la società di esempio Litware, Inc. Queste operazioni possono essere eseguite in qualsiasi società perché le configurazioni per la creazione di report elettronici sono condivise tra tutte le società.</span><span class="sxs-lookup"><span data-stu-id="5089f-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="5089f-107">Per completare questi passaggi, è necessario completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".</span><span class="sxs-lookup"><span data-stu-id="5089f-107">To complete these steps, you must first complete the steps in the "Create a configuration provider and mark it as active" procedure.</span></span>

1. <span data-ttu-id="5089f-108">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="5089f-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>

    <span data-ttu-id="5089f-109">Selezionare il provider di configurazione per la società di esempio "Litware, Inc."</span><span class="sxs-lookup"><span data-stu-id="5089f-109">Select the configuration provider for sample company, 'Litware, Inc.'</span></span> <span data-ttu-id="5089f-110">Se il provider di configurazione non viene visualizzato, è necessario innanzitutto completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".</span><span class="sxs-lookup"><span data-stu-id="5089f-110">If you don't see this configuration provider, you must first complete the steps in the "Create a configuration provider and mark it as active" procedure.</span></span>  
    
2. <span data-ttu-id="5089f-111">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="5089f-111">Click Reporting configurations.</span></span>

    <span data-ttu-id="5089f-112">Verrà creata una configurazione che contiene un modello dati per i documenti di pagamento elettronico.</span><span class="sxs-lookup"><span data-stu-id="5089f-112">You will create a configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="5089f-113">Questo modello dati verrà utilizzato successivamente come origine dati quando si crea il formato dei documenti di pagamento.</span><span class="sxs-lookup"><span data-stu-id="5089f-113">This data model will be used later as a data source when you create the format for the payment documents.</span></span>  

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="5089f-114">Crea una nuova configurazione di modello dati</span><span class="sxs-lookup"><span data-stu-id="5089f-114">Create a new data model configuration</span></span>
1. <span data-ttu-id="5089f-115">Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .</span><span class="sxs-lookup"><span data-stu-id="5089f-115">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="5089f-116">Nel campo Nome digitare "Pagamenti (modello semplificato)".</span><span class="sxs-lookup"><span data-stu-id="5089f-116">In the Name field, type 'Payments (simplified model)'.</span></span>
3. <span data-ttu-id="5089f-117">Nel campo Descrizione digitare "Configurazione modello di pagamento".</span><span class="sxs-lookup"><span data-stu-id="5089f-117">In the Description field, type 'Payment model configuration'.</span></span>

    <span data-ttu-id="5089f-118">Il provider di configurazione attiva viene inserito automaticamente in questo punto.</span><span class="sxs-lookup"><span data-stu-id="5089f-118">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="5089f-119">Tale provider potrà gestire la configurazione.</span><span class="sxs-lookup"><span data-stu-id="5089f-119">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="5089f-120">Altri provider possono utilizzare la configurazione, ma non potranno gestirla.</span><span class="sxs-lookup"><span data-stu-id="5089f-120">Other providers can use this configuration, but will not be able to maintain it.</span></span>  

4. <span data-ttu-id="5089f-121">Fare clic sul pulsante "Crea configurazione" per completare l'attività di creazione della configurazione</span><span class="sxs-lookup"><span data-stu-id="5089f-121">Click 'Create configuration' button to complete the configuration creation task</span></span>

## <a name="create-a-data-model"></a><span data-ttu-id="5089f-122">Creare un modello dati</span><span class="sxs-lookup"><span data-stu-id="5089f-122">Create a data model</span></span>
<span data-ttu-id="5089f-123">Si sta creando un nuovo modello dati per la configurazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="5089f-123">You're creating a new data model for the selected configuration.</span></span> <span data-ttu-id="5089f-124">Questa versione di configurazione avrà lo stato di bozza.</span><span class="sxs-lookup"><span data-stu-id="5089f-124">This configuration version will have a status of Draft.</span></span>  
1. <span data-ttu-id="5089f-125">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="5089f-125">Click Designer.</span></span>

## <a name="define-the-structure-of-a-party-participating-in-a-payment-process"></a><span data-ttu-id="5089f-126">Definire la struttura di una parte che partecipa a un processo di pagamento</span><span class="sxs-lookup"><span data-stu-id="5089f-126">Define the structure of a party participating in a payment process</span></span>
1. <span data-ttu-id="5089f-127">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="5089f-127">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="5089f-128">Digitare 'Party' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="5089f-128">In the Name field, type 'Party'.</span></span>
3. <span data-ttu-id="5089f-129">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="5089f-129">Click Add.</span></span>
4. <span data-ttu-id="5089f-130">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="5089f-130">Click New to open the drop dialog.</span></span>
5. <span data-ttu-id="5089f-131">Nel campo Nome digitare "Nome".</span><span class="sxs-lookup"><span data-stu-id="5089f-131">In the Name field, type 'Name'.</span></span>
6. <span data-ttu-id="5089f-132">Nel campo Tipo di articolo selezionare "Stringa".</span><span class="sxs-lookup"><span data-stu-id="5089f-132">In the Item type field, select 'String'.</span></span>
7. <span data-ttu-id="5089f-133">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="5089f-133">Click Add.</span></span>
8. <span data-ttu-id="5089f-134">Digitare 'Party' nel campo Trova.</span><span class="sxs-lookup"><span data-stu-id="5089f-134">In the Find field, type 'Party'.</span></span>
9. <span data-ttu-id="5089f-135">Fare clic su Trova precedente.</span><span class="sxs-lookup"><span data-stu-id="5089f-135">Click Find previous.</span></span>

## <a name="define-the-bank-structure-for-this-model"></a><span data-ttu-id="5089f-136">Definire la struttura della banca per il modello</span><span class="sxs-lookup"><span data-stu-id="5089f-136">Define the bank structure for this model</span></span>
1. <span data-ttu-id="5089f-137">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="5089f-137">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="5089f-138">Nel campo Nome digitare "Agente".</span><span class="sxs-lookup"><span data-stu-id="5089f-138">In the Name field, type 'Agent'.</span></span>
3. <span data-ttu-id="5089f-139">Nel campo Tipo di articolo selezionare "Record".</span><span class="sxs-lookup"><span data-stu-id="5089f-139">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="5089f-140">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="5089f-140">Click Add.</span></span>
5. <span data-ttu-id="5089f-141">Nel campo Descrizione immettere 'Istituto finanziario, ad esempio una banca, responsabile di un conto per la parte (debitore/creditore).'.</span><span class="sxs-lookup"><span data-stu-id="5089f-141">In the Description field, enter 'Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).'.</span></span>

    <span data-ttu-id="5089f-142">Istituto finanziario, ad esempio una banca, responsabile di un conto per la parte (debitore/creditore).</span><span class="sxs-lookup"><span data-stu-id="5089f-142">Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).</span></span>  

6. <span data-ttu-id="5089f-143">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="5089f-143">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="5089f-144">Nel campo Nome digitare "Nome".</span><span class="sxs-lookup"><span data-stu-id="5089f-144">In the Name field, type 'Name'.</span></span> 
8. <span data-ttu-id="5089f-145">Nel campo Tipo di articolo selezionare "Stringa".</span><span class="sxs-lookup"><span data-stu-id="5089f-145">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="5089f-146">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="5089f-146">Click Add.</span></span>
10. <span data-ttu-id="5089f-147">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="5089f-147">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="5089f-148">Nel campo Nome digitare "SWIFT".</span><span class="sxs-lookup"><span data-stu-id="5089f-148">In the Name field, type 'SWIFT'.</span></span>
12. <span data-ttu-id="5089f-149">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="5089f-149">Click Add.</span></span>
13. <span data-ttu-id="5089f-150">Nel campo Descrizione immettere 'Codice di identificazione bancario'.</span><span class="sxs-lookup"><span data-stu-id="5089f-150">In the Description field, enter 'Bank identification code'.</span></span> 
14. <span data-ttu-id="5089f-151">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="5089f-151">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="5089f-152">Nel campo Nome digitare "RoutingNumber".</span><span class="sxs-lookup"><span data-stu-id="5089f-152">In the Name field, type 'RoutingNumber'.</span></span>
16. <span data-ttu-id="5089f-153">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="5089f-153">Click Add.</span></span>
17. <span data-ttu-id="5089f-154">Nel campo Descrizione immettere 'Numero di registrazione'.</span><span class="sxs-lookup"><span data-stu-id="5089f-154">In the Description field, enter 'Routing number'.</span></span>
18. <span data-ttu-id="5089f-155">Fare clic su Trova precedente.</span><span class="sxs-lookup"><span data-stu-id="5089f-155">Click Find previous.</span></span>

## <a name="define-the-bank-account-structure-for-this-model"></a><span data-ttu-id="5089f-156">Definire la struttura del conto bancario per il modello</span><span class="sxs-lookup"><span data-stu-id="5089f-156">Define the bank account structure for this model</span></span>
1. <span data-ttu-id="5089f-157">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="5089f-157">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="5089f-158">Nel campo Nome digitare "Conto".</span><span class="sxs-lookup"><span data-stu-id="5089f-158">In the Name field, type 'Account'.</span></span> 
3. <span data-ttu-id="5089f-159">Nel campo Tipo di articolo selezionare "Record".</span><span class="sxs-lookup"><span data-stu-id="5089f-159">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="5089f-160">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="5089f-160">Click Add.</span></span>
5. <span data-ttu-id="5089f-161">Nel campo Descrizione, immettere 'Identificazione di un conto di una parte di un istituto finanziario, ad esempio una banca.'.</span><span class="sxs-lookup"><span data-stu-id="5089f-161">In the Description field, enter 'Identification of an account of a party in a financial institution (for instance, a bank).'.</span></span>

    <span data-ttu-id="5089f-162">Identificazione di un conto di una parte di un istituto finanziario, ad esempio una banca.</span><span class="sxs-lookup"><span data-stu-id="5089f-162">Identification of an account of a party in a financial institution (for instance, a bank).</span></span>  

6. <span data-ttu-id="5089f-163">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="5089f-163">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="5089f-164">Nel campo Nome digitare "Valuta".</span><span class="sxs-lookup"><span data-stu-id="5089f-164">In the Name field, type 'Currency'.</span></span> 
8. <span data-ttu-id="5089f-165">Nel campo Tipo di articolo selezionare "Stringa".</span><span class="sxs-lookup"><span data-stu-id="5089f-165">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="5089f-166">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="5089f-166">Click Add.</span></span>
10. <span data-ttu-id="5089f-167">Nel campo Descrizione immettere 'Codice valuta'.</span><span class="sxs-lookup"><span data-stu-id="5089f-167">In the Description field, enter 'Currency code'.</span></span>
11. <span data-ttu-id="5089f-168">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="5089f-168">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="5089f-169">Nel campo Nome digitare "Numero".</span><span class="sxs-lookup"><span data-stu-id="5089f-169">In the Name field, type 'Number'.</span></span> 
13. <span data-ttu-id="5089f-170">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="5089f-170">Click Add.</span></span>
14. <span data-ttu-id="5089f-171">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="5089f-171">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="5089f-172">Nel campo nome digitare "IBAN".</span><span class="sxs-lookup"><span data-stu-id="5089f-172">In the Name field, type 'IBAN'.</span></span> 
16. <span data-ttu-id="5089f-173">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="5089f-173">Click Add.</span></span>
17. <span data-ttu-id="5089f-174">Nel campo Descrizione immettere 'International Bank Account Number (numero di conto bancario internazionale)'.</span><span class="sxs-lookup"><span data-stu-id="5089f-174">In the Description field, enter 'International bank account number'.</span></span>

## <a name="define-the-payment-message-structure-for-credit-transfer-payment-type"></a><span data-ttu-id="5089f-175">Definire la struttura del messaggio di pagamento per il tipo di pagamento con bonifico</span><span class="sxs-lookup"><span data-stu-id="5089f-175">Define the payment message structure for credit transfer payment type</span></span>
1. <span data-ttu-id="5089f-176">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="5089f-176">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="5089f-177">Nel campo Nuovo nodo come immettere 'Radice modello'.</span><span class="sxs-lookup"><span data-stu-id="5089f-177">In the New node as a field, enter 'Model root'.</span></span>
3. <span data-ttu-id="5089f-178">Nel campo Nome digitare "CustomerCreditTransferInitiation".</span><span class="sxs-lookup"><span data-stu-id="5089f-178">In the Name field, type 'CustomerCreditTransferInitiation'.</span></span>
4. <span data-ttu-id="5089f-179">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="5089f-179">Click Add.</span></span>
5. <span data-ttu-id="5089f-180">Nel campo Trova digitare 'CustomerCreditTransferInitiation'.</span><span class="sxs-lookup"><span data-stu-id="5089f-180">In the Find field, type 'CustomerCreditTransferInitiation'.</span></span> 
6. <span data-ttu-id="5089f-181">Fare clic su Trova precedente.</span><span class="sxs-lookup"><span data-stu-id="5089f-181">Click Find previous.</span></span>
7. <span data-ttu-id="5089f-182">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="5089f-182">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="5089f-183">Nel campo Nome digitare "MessageIdentification".</span><span class="sxs-lookup"><span data-stu-id="5089f-183">In the Name field, type 'MessageIdentification'.</span></span> 
9. <span data-ttu-id="5089f-184">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="5089f-184">Click Add.</span></span>
10. <span data-ttu-id="5089f-185">Nel campo Descrizione immettere 'Riferimento punto a punto assegnato dalla parte che impartisce le istruzioni e inviato alla parte successiva per identificare un messaggio'.</span><span class="sxs-lookup"><span data-stu-id="5089f-185">In the Description field, enter 'The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.'.</span></span>

    <span data-ttu-id="5089f-186">Riferimento punto a punto assegnato dalla parte che impartisce le istruzioni e inviato alla parte successiva per identificare un messaggio.</span><span class="sxs-lookup"><span data-stu-id="5089f-186">The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.</span></span>  

11. <span data-ttu-id="5089f-187">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="5089f-187">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="5089f-188">Nel campo Nome digitare "ProcessingDateTime".</span><span class="sxs-lookup"><span data-stu-id="5089f-188">In the Name field, type 'ProcessingDateTime'.</span></span>
13. <span data-ttu-id="5089f-189">Nel campo Tipo di articolo selezionare "DateTime".</span><span class="sxs-lookup"><span data-stu-id="5089f-189">In the Item type field, select 'DateTime'.</span></span>
14. <span data-ttu-id="5089f-190">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="5089f-190">Click Add.</span></span>
15. <span data-ttu-id="5089f-191">Nel campo Descrizione immettere 'Data e ora di creazione del messaggio di pagamento.'.</span><span class="sxs-lookup"><span data-stu-id="5089f-191">In the Description field, enter 'Date and time at which the payment message was created.'.</span></span> 
16. <span data-ttu-id="5089f-192">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="5089f-192">Click New to open the drop dialog.</span></span>

    <span data-ttu-id="5089f-193">Definire la struttura della transazione di pagamento per il modello.</span><span class="sxs-lookup"><span data-stu-id="5089f-193">Define the payment transaction structure for this model.</span></span>  

17. <span data-ttu-id="5089f-194">Nel campo Nome digitare "Pagamenti".</span><span class="sxs-lookup"><span data-stu-id="5089f-194">In the Name field, type 'Payments'.</span></span>
18. <span data-ttu-id="5089f-195">Nel campo Tipo di articolo selezionare "Elenco di record".</span><span class="sxs-lookup"><span data-stu-id="5089f-195">In the Item type field, select 'Record list'.</span></span>
19. <span data-ttu-id="5089f-196">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="5089f-196">Click Add.</span></span>
20. <span data-ttu-id="5089f-197">Nel campo Descrizione immettere "Righe pagamento del messaggio corrente".</span><span class="sxs-lookup"><span data-stu-id="5089f-197">In the Description field, enter 'Payment lines of the current message'.</span></span>
21. <span data-ttu-id="5089f-198">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="5089f-198">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="5089f-199">Nel campo Nome digitare "Creditore".</span><span class="sxs-lookup"><span data-stu-id="5089f-199">In the Name field, type 'Creditor'.</span></span> 
23. <span data-ttu-id="5089f-200">Nel campo Tipo di articolo selezionare "Record".</span><span class="sxs-lookup"><span data-stu-id="5089f-200">In the Item type field, select 'Record'.</span></span>
24. <span data-ttu-id="5089f-201">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="5089f-201">Click Add.</span></span>
25. <span data-ttu-id="5089f-202">Nel campo Descrizione immettere 'Parte a cui è dovuta una somma di denaro.'.</span><span class="sxs-lookup"><span data-stu-id="5089f-202">In the Description field, enter 'Party to which an amount of money is due.'.</span></span> 
26. <span data-ttu-id="5089f-203">Fare clic su Cambia riferimento articolo.</span><span class="sxs-lookup"><span data-stu-id="5089f-203">Click Switch item reference.</span></span>
27. <span data-ttu-id="5089f-204">Digitare 'Party' nel campo Trova.</span><span class="sxs-lookup"><span data-stu-id="5089f-204">In the Find field, type 'Party'.</span></span>
28. <span data-ttu-id="5089f-205">Fare clic su Trova successivo.</span><span class="sxs-lookup"><span data-stu-id="5089f-205">Click Find next.</span></span>
29. <span data-ttu-id="5089f-206">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="5089f-206">Click OK.</span></span>
30. <span data-ttu-id="5089f-207">Nel campo Trova digitare 'Pagamenti'.</span><span class="sxs-lookup"><span data-stu-id="5089f-207">In the Find field, type 'Payments'.</span></span>
31. <span data-ttu-id="5089f-208">Fare clic su Trova successivo.</span><span class="sxs-lookup"><span data-stu-id="5089f-208">Click Find next.</span></span>
32. <span data-ttu-id="5089f-209">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="5089f-209">Click New to open the drop dialog.</span></span>
33. <span data-ttu-id="5089f-210">Nel campo nome digitare "Debitore".</span><span class="sxs-lookup"><span data-stu-id="5089f-210">In the Name field, type 'Debtor'.</span></span> 
34. <span data-ttu-id="5089f-211">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="5089f-211">Click Add.</span></span>
35. <span data-ttu-id="5089f-212">Nel campo Descrizione immettere 'Parte che deve una somma di denaro al creditore (finale).'.</span><span class="sxs-lookup"><span data-stu-id="5089f-212">In the Description field, enter 'Party that owes an amount of money to the (ultimate) creditor.'.</span></span>
36. <span data-ttu-id="5089f-213">Fare clic su Cambia riferimento articolo.</span><span class="sxs-lookup"><span data-stu-id="5089f-213">Click Switch item reference.</span></span>
37. <span data-ttu-id="5089f-214">Digitare 'Party' nel campo Trova.</span><span class="sxs-lookup"><span data-stu-id="5089f-214">In the Find field, type 'Party'.</span></span>
38. <span data-ttu-id="5089f-215">Fare clic su Trova successivo.</span><span class="sxs-lookup"><span data-stu-id="5089f-215">Click Find next.</span></span>
39. <span data-ttu-id="5089f-216">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="5089f-216">Click OK.</span></span>
40. <span data-ttu-id="5089f-217">Fare clic su Trova successivo.</span><span class="sxs-lookup"><span data-stu-id="5089f-217">Click Find next.</span></span>
41. <span data-ttu-id="5089f-218">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="5089f-218">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="5089f-219">Nel campo Nome digitare "Descrizione".</span><span class="sxs-lookup"><span data-stu-id="5089f-219">In the Name field, type 'Description'.</span></span>
43. <span data-ttu-id="5089f-220">Nel campo Tipo di articolo selezionare "Stringa".</span><span class="sxs-lookup"><span data-stu-id="5089f-220">In the Item type field, select 'String'.</span></span>
44. <span data-ttu-id="5089f-221">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="5089f-221">Click Add.</span></span>
45. <span data-ttu-id="5089f-222">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="5089f-222">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="5089f-223">Nel campo Nome digitare "Valuta".</span><span class="sxs-lookup"><span data-stu-id="5089f-223">In the Name field, type 'Currency'.</span></span>
47. <span data-ttu-id="5089f-224">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="5089f-224">Click Add.</span></span>
48. <span data-ttu-id="5089f-225">Nel campo Descrizione immettere 'Codice valuta'.</span><span class="sxs-lookup"><span data-stu-id="5089f-225">In the Description field, enter 'Currency code'.</span></span>
49. <span data-ttu-id="5089f-226">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="5089f-226">Click New to open the drop dialog.</span></span>
50. <span data-ttu-id="5089f-227">Nel campo Nome digitare "TransactionDate".</span><span class="sxs-lookup"><span data-stu-id="5089f-227">In the Name field, type 'TransactionDate'.</span></span> 
51. <span data-ttu-id="5089f-228">Nel campo Tipo di articolo selezionare "Data".</span><span class="sxs-lookup"><span data-stu-id="5089f-228">In the Item type field, select 'Date'.</span></span>
52. <span data-ttu-id="5089f-229">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="5089f-229">Click Add.</span></span>
53. <span data-ttu-id="5089f-230">Nel campo Descrizione immettere 'Data della transazione'.</span><span class="sxs-lookup"><span data-stu-id="5089f-230">In the Description field, enter 'Transaction date'.</span></span> 
54. <span data-ttu-id="5089f-231">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="5089f-231">Click New to open the drop dialog.</span></span>
55. <span data-ttu-id="5089f-232">Nel campo Nome digitare "InstructedAmount".</span><span class="sxs-lookup"><span data-stu-id="5089f-232">In the Name field, type 'InstructedAmount'.</span></span>  
56. <span data-ttu-id="5089f-233">Nel campo Tipo di articolo selezionare "Reale".</span><span class="sxs-lookup"><span data-stu-id="5089f-233">In the Item type field, select 'Real'.</span></span>
57. <span data-ttu-id="5089f-234">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="5089f-234">Click Add.</span></span>
58. <span data-ttu-id="5089f-235">Nel campo Descrizione immettere 'Somma di denaro da trasferire tra il debitore e il creditore al lordo delle detrazione di oneri.</span><span class="sxs-lookup"><span data-stu-id="5089f-235">In the Description field, enter 'The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="5089f-236">L'importo deve essere espresso nella valuta indicata dalla parte che inizia la transazione".</span><span class="sxs-lookup"><span data-stu-id="5089f-236">The amount should be expressed in the currency as ordered by the initiating party.'.</span></span>

    <span data-ttu-id="5089f-237">Somma di denaro da trasferire tra il debitore e il creditore al lordo delle detrazione di oneri.</span><span class="sxs-lookup"><span data-stu-id="5089f-237">The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="5089f-238">L'importo deve essere espresso nella valuta indicata dalla parte che inizia la transazione.</span><span class="sxs-lookup"><span data-stu-id="5089f-238">The amount should be expressed in the currency as ordered by the initiating party.</span></span>  

59. <span data-ttu-id="5089f-239">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="5089f-239">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="5089f-240">Nel campo Nome digitare "End2EndID".</span><span class="sxs-lookup"><span data-stu-id="5089f-240">In the Name field, type 'End2EndID'.</span></span> 
61. <span data-ttu-id="5089f-241">Nel campo Tipo di articolo selezionare "Stringa".</span><span class="sxs-lookup"><span data-stu-id="5089f-241">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="5089f-242">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="5089f-242">Click Add.</span></span>
63. <span data-ttu-id="5089f-243">Nel campo Descrizione immettere 'Identificazione univoca assegnata dalla parte che inizia la transazione.</span><span class="sxs-lookup"><span data-stu-id="5089f-243">In the Description field, enter 'The unique identification assigned by the initiating party.</span></span> <span data-ttu-id="5089f-244">L'identificazione viene passata senza modifiche lungo l'intera catena end-to-end".</span><span class="sxs-lookup"><span data-stu-id="5089f-244">This identification is passed on, unchanged, throughout the entire end-to-end chain.'.</span></span> 
64. <span data-ttu-id="5089f-245">Nel campo Nome digitare "PaymentModel".</span><span class="sxs-lookup"><span data-stu-id="5089f-245">In the Name field, type 'PaymentModel'.</span></span>

    <span data-ttu-id="5089f-246">Il nome PaymentModel è in linea con le interfacce predefinite delle forme di pagamento.</span><span class="sxs-lookup"><span data-stu-id="5089f-246">The PaymentModel name aligns with predefined interfaces of payment forms.</span></span>  

65. <span data-ttu-id="5089f-247">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="5089f-247">Click Save.</span></span>
66. <span data-ttu-id="5089f-248">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5089f-248">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]