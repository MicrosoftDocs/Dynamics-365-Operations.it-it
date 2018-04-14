--- 
title: Selezionare la definizione del modello dati durante la creazione del formato per la creazione di report elettronici (ER)
description: "Per completare i passaggi in questa procedura, è necessario prima completare i passaggi della procedura \"ER Creare un provider di configurazione e contrassegnarlo come attivo\"."
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
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
ms.openlocfilehash: e560daa19b30c3f12e2b7a414580f89c93dfc31a
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---
# <a name="select-data-model-definition-while-creating-format-for-electronic-reporting-er"></a><span data-ttu-id="272ec-103">Selezionare la definizione del modello dati durante la creazione del formato per la creazione di report elettronici (ER)</span><span class="sxs-lookup"><span data-stu-id="272ec-103">Select data model definition while creating format for electronic reporting (ER)</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="272ec-104">Per completare i passaggi in questa procedura, è necessario prima completare i passaggi della procedura "ER Creare un provider di configurazione e contrassegnarlo come attivo".</span><span class="sxs-lookup"><span data-stu-id="272ec-104">To complete the steps in this procedure, you must first complete the procedure, ER Create a configuration provider and mark it as active.</span></span> 

<span data-ttu-id="272ec-105">Questa procedura descrive come un elemento radice del modello può essere selezionato come definizione del modello dati per l'inserimento di una configurazione di formato ER progettata per generare documenti elettronici.</span><span class="sxs-lookup"><span data-stu-id="272ec-105">This procedure shows how a model’s root item can be selected as a data model definition for inserting an Electronic reporting (ER) format configuration that is designed to generate electronic documents.</span></span> <span data-ttu-id="272ec-106">In questa procedura verrà aggiunta una nuova configurazione di formato ER per la società di esempio Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="272ec-106">In this procedure, you will add a new ER format configuration for the sample company Litware, Inc.</span></span> 

<span data-ttu-id="272ec-107">Questa procedura viene creata per utenti con il ruolo di amministratore di sistema o di sviluppatore di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="272ec-107">This procedure is intended for users who have the System administrator or Electronic reporting developer role assigned to them.</span></span> <span data-ttu-id="272ec-108">I passaggi possono essere completati mediante un set di dati qualsiasi.</span><span class="sxs-lookup"><span data-stu-id="272ec-108">The steps can be completed by using any dataset.</span></span>

1. <span data-ttu-id="272ec-109">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="272ec-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="272ec-110">Verificare che il provider di configurazione per la società di esempio Litware, Inc. sia disponibile e contrassegnato come attivo.</span><span class="sxs-lookup"><span data-stu-id="272ec-110">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as Active.</span></span> <span data-ttu-id="272ec-111">Se il provider di configurazione non è visualizzato, è necessario innanzitutto completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".</span><span class="sxs-lookup"><span data-stu-id="272ec-111">If you don’t see this configuration provider, complete the steps in the procedure, Create a configuration provider and mark it as active.</span></span>  
2. <span data-ttu-id="272ec-112">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="272ec-112">Click Reporting configurations.</span></span>

## <a name="add-a-new-er-data-model-configuration"></a><span data-ttu-id="272ec-113">Aggiungere una nuova configurazione del modello dati ER</span><span class="sxs-lookup"><span data-stu-id="272ec-113">Add a new ER data model configuration</span></span>
1. <span data-ttu-id="272ec-114">Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .</span><span class="sxs-lookup"><span data-stu-id="272ec-114">Click Create configuration to open the drop dialog.</span></span>
    * <span data-ttu-id="272ec-115">Aggiungiamo una nuova configurazione del modello ER contenente un modello dati progettato per essere utilizzato come origine dati per la generazione di report ER.</span><span class="sxs-lookup"><span data-stu-id="272ec-115">We add a new ER model configuration containing a data model that is designed to be used as data source for generation ER reports.</span></span>  
2. <span data-ttu-id="272ec-116">Nel campo Nome digitare "Modello di pagamento (fittizio)".</span><span class="sxs-lookup"><span data-stu-id="272ec-116">In the Name field, type 'Payment model (fictitious)'.</span></span>
    * <span data-ttu-id="272ec-117">Modello di pagamento (fittizio)</span><span class="sxs-lookup"><span data-stu-id="272ec-117">Payment model (fictitious)</span></span>  
3. <span data-ttu-id="272ec-118">Fare clic su Crea configurazione.</span><span class="sxs-lookup"><span data-stu-id="272ec-118">Click Create configuration.</span></span>
4. <span data-ttu-id="272ec-119">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="272ec-119">Click Designer.</span></span>
    * <span data-ttu-id="272ec-120">Aprire la finestra di progettazione ER per specificare la struttura del modello dati della configurazione.</span><span class="sxs-lookup"><span data-stu-id="272ec-120">Open the ER designer to specify the structure of data model of this configuration.</span></span>  
    * <span data-ttu-id="272ec-121">Si supponga di progettare il modello dati per il dominio dei pagamenti aziendali per supportare 2 metodi di pagamento, ovvero bonifico e addebito diretto.</span><span class="sxs-lookup"><span data-stu-id="272ec-121">Assume that we design the data model for payments business domain to support 2 payment methods – credit transfer and direct debit ones.</span></span>  
5. <span data-ttu-id="272ec-122">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="272ec-122">Click New to open the drop dialog.</span></span>
6. <span data-ttu-id="272ec-123">Nel campo Nome digitare "Pagamenti - bonifico".</span><span class="sxs-lookup"><span data-stu-id="272ec-123">In the Name field, type 'Payments – credit transfer'.</span></span>
    * <span data-ttu-id="272ec-124">Pagamenti - bonifico</span><span class="sxs-lookup"><span data-stu-id="272ec-124">Payments – credit transfer</span></span>  
7. <span data-ttu-id="272ec-125">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="272ec-125">Click Add.</span></span>
8. <span data-ttu-id="272ec-126">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="272ec-126">Click New to open the drop dialog.</span></span>
9. <span data-ttu-id="272ec-127">Nel campo Nuovo nodo come immettere 'Radice modello'.</span><span class="sxs-lookup"><span data-stu-id="272ec-127">In the New node as a field, enter 'Model root'.</span></span>
10. <span data-ttu-id="272ec-128">Nel campo Nome digitare "Pagamenti - addebito diretto".</span><span class="sxs-lookup"><span data-stu-id="272ec-128">In the Name field, type 'Payments – direct debit'.</span></span>
    * <span data-ttu-id="272ec-129">Pagamenti - addebito diretto</span><span class="sxs-lookup"><span data-stu-id="272ec-129">Payments – direct debit</span></span>  
11. <span data-ttu-id="272ec-130">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="272ec-130">Click Add.</span></span>
12. <span data-ttu-id="272ec-131">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="272ec-131">Click Save.</span></span>
13. <span data-ttu-id="272ec-132">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="272ec-132">Close the page.</span></span>
14. <span data-ttu-id="272ec-133">Fare clic su Cambia stato.</span><span class="sxs-lookup"><span data-stu-id="272ec-133">Click Change status.</span></span>
    * <span data-ttu-id="272ec-134">Completare la versione bozza del modello per renderlo disponibile nei mapping e nei formati del nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="272ec-134">Complete the draft version of the model to make it available in new model mappings and formats.</span></span>  
15. <span data-ttu-id="272ec-135">Fare clic su Completa.</span><span class="sxs-lookup"><span data-stu-id="272ec-135">Click Complete.</span></span>
16. <span data-ttu-id="272ec-136">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="272ec-136">Click OK.</span></span>

## <a name="start-to-enter-a-new-er-format-configuration"></a><span data-ttu-id="272ec-137">Iniziare a immettere una nuova configurazione dei formati ER</span><span class="sxs-lookup"><span data-stu-id="272ec-137">Start to enter a new ER format configuration</span></span>
1. <span data-ttu-id="272ec-138">Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .</span><span class="sxs-lookup"><span data-stu-id="272ec-138">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="272ec-139">Nel campo Nuovo immettere "Formato in base al modello dati Modello di pagamento (fittizio)".</span><span class="sxs-lookup"><span data-stu-id="272ec-139">In the New field, enter 'Format based on data model Payment model (fictitious)'.</span></span>
3. <span data-ttu-id="272ec-140">Nel campo Definizione modello dati immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="272ec-140">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="272ec-141">Si noti che tutti gli elementi radice sono attualmente disponibili per la selezione come definizione di modello dati.</span><span class="sxs-lookup"><span data-stu-id="272ec-141">Note that all root items of the selected data model are currently available for selection as a data model definition.</span></span> <span data-ttu-id="272ec-142">È possibile continuare la progettazione del formato utilizzando uno degli elementi radice necessari del modello dati.</span><span class="sxs-lookup"><span data-stu-id="272ec-142">You can continue to design your format by using any of the required root items of the data model.</span></span> <span data-ttu-id="272ec-143">Un mapping di modello mancante per l'elemento radice selezionato non impedisce di continuare.</span><span class="sxs-lookup"><span data-stu-id="272ec-143">A missing model mapping for the selected root item doesn't prevent you from continuing.</span></span>  
4. <span data-ttu-id="272ec-144">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="272ec-144">Close the page.</span></span>

## <a name="add-a-new-er-model-mapping-configuration"></a><span data-ttu-id="272ec-145">Aggiungere una nuova configurazione del mapping di modello ER</span><span class="sxs-lookup"><span data-stu-id="272ec-145">Add a new ER model mapping configuration</span></span>
1. <span data-ttu-id="272ec-146">Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .</span><span class="sxs-lookup"><span data-stu-id="272ec-146">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="272ec-147">Nel campo Nuovo immettere "Mapping modello in base al modello dati Modello di pagamento (fittizio)".</span><span class="sxs-lookup"><span data-stu-id="272ec-147">In the New field, enter 'Model Mapping based on data model Payment model (fictitious)'.</span></span>
3. <span data-ttu-id="272ec-148">Nel campo Nome digitare "Mapping modello di pagamento (fittizio)".</span><span class="sxs-lookup"><span data-stu-id="272ec-148">In the Name field, type 'Payment model mappings (fictitious)'.</span></span>
    * <span data-ttu-id="272ec-149">Mapping di modelli di pagamento (fittizio)</span><span class="sxs-lookup"><span data-stu-id="272ec-149">Payment model mappings (fictitious)</span></span>  
4. <span data-ttu-id="272ec-150">Nel campo Definizione modello dati immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="272ec-150">In the Data model definition field, enter or select a value.</span></span>
5. <span data-ttu-id="272ec-151">Fare clic su Crea configurazione.</span><span class="sxs-lookup"><span data-stu-id="272ec-151">Click Create configuration.</span></span>

## <a name="design-er-model-mappings"></a><span data-ttu-id="272ec-152">Progettare mapping di modello ER</span><span class="sxs-lookup"><span data-stu-id="272ec-152">Design ER model mappings</span></span>
1. <span data-ttu-id="272ec-153">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="272ec-153">Click Designer.</span></span>
    * <span data-ttu-id="272ec-154">Utilizzare la finestra di progettazione ER per specificare i mapping di modello per gli elementi radice necessari.</span><span class="sxs-lookup"><span data-stu-id="272ec-154">Use the ER designer to specify the model mappings for the required root items.</span></span>  
2. <span data-ttu-id="272ec-155">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="272ec-155">Click Designer.</span></span>
    * <span data-ttu-id="272ec-156">Simulare l'impostazione del mapping di modello selezionato per l'elemento radice del modello selezionato.</span><span class="sxs-lookup"><span data-stu-id="272ec-156">Simulate setting of selected model mapping for the selected model’s root item.</span></span>  
3. <span data-ttu-id="272ec-157">Nella struttura selezionare "Dynamics 365 for Operations\Table records".</span><span class="sxs-lookup"><span data-stu-id="272ec-157">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
4. <span data-ttu-id="272ec-158">Fare clic su Aggiungi radice.</span><span class="sxs-lookup"><span data-stu-id="272ec-158">Click Add root.</span></span>
5. <span data-ttu-id="272ec-159">Nel campo Nome digitare "Contabilità generale".</span><span class="sxs-lookup"><span data-stu-id="272ec-159">In the Name field, type 'Ledger'.</span></span>
6. <span data-ttu-id="272ec-160">Nel campo Tabella digitare "LedgerJournalTrans".</span><span class="sxs-lookup"><span data-stu-id="272ec-160">In the Table field, type 'LedgerJournalTrans'.</span></span>
    * <span data-ttu-id="272ec-161">LedgerJournalTrans</span><span class="sxs-lookup"><span data-stu-id="272ec-161">LedgerJournalTrans</span></span>  
7. <span data-ttu-id="272ec-162">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="272ec-162">Click OK.</span></span>
8. <span data-ttu-id="272ec-163">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="272ec-163">Click Save.</span></span>
9. <span data-ttu-id="272ec-164">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="272ec-164">Close the page.</span></span>
10. <span data-ttu-id="272ec-165">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="272ec-165">Close the page.</span></span>

## <a name="start-to-enter-another-new-er-format-configuration"></a><span data-ttu-id="272ec-166">Iniziare a immettere un'altra nuova configurazione dei formati ER</span><span class="sxs-lookup"><span data-stu-id="272ec-166">Start to enter another new ER format configuration</span></span>
1. <span data-ttu-id="272ec-167">Nella struttura selezionare "Payment model (fictitious)".</span><span class="sxs-lookup"><span data-stu-id="272ec-167">In the tree, select 'Payment model (fictitious)'.</span></span>
2. <span data-ttu-id="272ec-168">Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .</span><span class="sxs-lookup"><span data-stu-id="272ec-168">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="272ec-169">Nel campo Nuovo immettere "Formato in base al modello dati Modello di pagamento (fittizio)".</span><span class="sxs-lookup"><span data-stu-id="272ec-169">In the New field, enter 'Format based on data model Payment model (fictitious)'.</span></span>
4. <span data-ttu-id="272ec-170">Nel campo Definizione modello dati immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="272ec-170">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="272ec-171">Si noti che ora solo un elemento radice è disponibile per eseguire il mapping a origini dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="272ec-171">Note that now only one root item is available to map to the application data sources.</span></span> <span data-ttu-id="272ec-172">Quando viene introdotto almeno un mapping di modello, solo gli elementi radice del modello che sono mappati alle origini dati dell'applicazione possono essere selezionati come modello di definizione mentre il formato ER viene aggiunto.</span><span class="sxs-lookup"><span data-stu-id="272ec-172">When at least one model mapping is introduced, only the model’s root items that are mapped to application data sources can be selected as a model definition while the ER format is added.</span></span>   
5. <span data-ttu-id="272ec-173">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="272ec-173">Close the page.</span></span>


