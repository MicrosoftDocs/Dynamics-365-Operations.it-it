--- 
title: ER Progettare una configurazione per la creazione di report nel formato OPENXML (novembre 2016)
description: "I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare una nuova configurazione per la creazione di report elettronici (ER) che contiene un modello per la generazione di documenti elettronici in formato OPENXML."
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERDataSourceAddDropDialog, ERModelGroupByFunctionEditor, VendPaymMode, LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 3e6b6b16f202af051ccff02051eb438ea49ff6da
ms.contentlocale: it-it
ms.lasthandoff: 10/16/2018

---
# <a name="er-design-a-configuration-for-generating-reports-in-openxml-format-november-2016"></a><span data-ttu-id="cb1c4-103">ER Progettare una configurazione per la creazione di report nel formato OPENXML (novembre 2016)</span><span class="sxs-lookup"><span data-stu-id="cb1c4-103">ER Design a configuration for generating reports in OPENXML format (November 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cb1c4-104">I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare una nuova configurazione per la creazione di report elettronici (ER) che contiene un modello per la generazione di documenti elettronici in formato OPENXML.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a template for generating electronic documents in OPENXML format.</span></span> <span data-ttu-id="cb1c4-105">La configurazione verrà utilizzata per elaborare i pagamenti fornitore.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-105">This configuration will be used for processing vendor payments.</span></span>



<span data-ttu-id="cb1c4-106">In questo esempio verrà creata una configurazione per la società di esempio Litware, Inc. Queste operazioni possono essere eseguite nella società GBSI.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in GBSI company.</span></span>



<span data-ttu-id="cb1c4-107">Per completare questi passaggi, è necessario completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-107">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span> <span data-ttu-id="cb1c4-108">È inoltre necessario disporre di un file Excel che verrà importato in fase di creazione del modello.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-108">You must also have an Excel file which will be imported when creating the template.</span></span> <span data-ttu-id="cb1c4-109">È possibile accedere a questo file dal [Modello di Report di pagamento](https://go.microsoft.com/fwlink/?linkid=862266).</span><span class="sxs-lookup"><span data-stu-id="cb1c4-109">This file can be accessed from the [Template of Payment Report](https://go.microsoft.com/fwlink/?linkid=862266).</span></span>


## <a name="upload-the-payments-data-model-configuration"></a><span data-ttu-id="cb1c4-110">Caricare la configurazione del modello dati Pagamenti</span><span class="sxs-lookup"><span data-stu-id="cb1c4-110">Upload the Payments data model configuration</span></span>
1. <span data-ttu-id="cb1c4-111">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-111">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="cb1c4-112">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-112">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="cb1c4-113">Selezionare il provider di configurazione per la società di esempio Litware, Inc. Se il provider di configurazione non viene visualizzato, è necessario innanzitutto completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-113">Select the configuration provider for sample company, Litware, Inc. If you don’t see this configuration provider, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>  
3. <span data-ttu-id="cb1c4-114">Fare clic su Imposta attivo.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-114">Click Set active.</span></span>
4. <span data-ttu-id="cb1c4-115">Fare clic su Archivi.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-115">Click Repositories.</span></span>
    * <span data-ttu-id="cb1c4-116">Selezionare un archivio per il tipo Risorse Operations, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-116">Select a repository for the Operations Resources type, if available.</span></span> <span data-ttu-id="cb1c4-117">Se è disponibile, ignorare i passaggi seguenti che riguardano la creazione di un nuovo archivio.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-117">If its available, skip the following steps about creating a new repository.</span></span>  
5. <span data-ttu-id="cb1c4-118">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-118">Click Add to open the drop dialog.</span></span>
6. <span data-ttu-id="cb1c4-119">Nel campo Tipo di archivio di configurazioni immettere 'Risorse operative'.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-119">In the Configuration repository type field, enter 'Operations resources'.</span></span>
7. <span data-ttu-id="cb1c4-120">Fare clic su Crea archivio.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-120">Click Create repository.</span></span>
8. <span data-ttu-id="cb1c4-121">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-121">Click OK.</span></span>
9. <span data-ttu-id="cb1c4-122">Fare clic su Apri.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-122">Click Open.</span></span>
10. <span data-ttu-id="cb1c4-123">Nella struttura selezionare "Modello di pagamento".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-123">In the tree, select 'Payment model'.</span></span>
11. <span data-ttu-id="cb1c4-124">Fare clic su Importa.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-124">Click Import.</span></span>
    * <span data-ttu-id="cb1c4-125">Importare questo modello dati.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-125">Import this data model.</span></span> <span data-ttu-id="cb1c4-126">Verrà utilizzato come origine dati in nuova configurazione del formato.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-126">It will be used as a data source in a new format configuration.</span></span> <span data-ttu-id="cb1c4-127">Ignorare questo passaggio se la configurazione è già stata importata.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-127">Skip this step if this configuration has been already imported.</span></span>  
12. <span data-ttu-id="cb1c4-128">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-128">Click Yes.</span></span>
13. <span data-ttu-id="cb1c4-129">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-129">Close the page.</span></span>
14. <span data-ttu-id="cb1c4-130">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-130">Close the page.</span></span>

## <a name="create-a-new-format-configuration"></a><span data-ttu-id="cb1c4-131">Creare una nuova configurazione di formato</span><span class="sxs-lookup"><span data-stu-id="cb1c4-131">Create a new format configuration</span></span>
1. <span data-ttu-id="cb1c4-132">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-132">Click Reporting configurations.</span></span>
2. <span data-ttu-id="cb1c4-133">Nella struttura selezionare "Modello di pagamento".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-133">In the tree, select 'Payment model'.</span></span>
3. <span data-ttu-id="cb1c4-134">Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .</span><span class="sxs-lookup"><span data-stu-id="cb1c4-134">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="cb1c4-135">Nel campo Nuovo immettere "Formato in base al modello dati PaymentModel".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-135">In the New field, enter 'Format based on data model PaymentModel'.</span></span>
    * <span data-ttu-id="cb1c4-136">Creare un formato basato sul modello dati PaymentModel.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-136">Create a format that is based on the PaymentModel data model.</span></span>  
5. <span data-ttu-id="cb1c4-137">Nel campo Nome digitare "Report foglio di lavoro di esempio".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-137">In the Name field, type 'Sample worksheet report'.</span></span>
    * <span data-ttu-id="cb1c4-138">Report foglio di lavoro di esempio</span><span class="sxs-lookup"><span data-stu-id="cb1c4-138">Sample worksheet report</span></span>  
6. <span data-ttu-id="cb1c4-139">Nel campo Descrizione immettere “Report foglio di lavoro per i pagamenti dei fornitori".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-139">In the Description field, type 'Sample worksheet report for vendors’ payments'.</span></span>
    * <span data-ttu-id="cb1c4-140">Report foglio di lavoro per i pagamenti dei fornitori.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-140">Sample worksheet report for vendors’ payments.</span></span>  
7. <span data-ttu-id="cb1c4-141">Nel campo Definizione modello dati immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-141">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="cb1c4-142">Selezionare la definizione "CustomerCreditTransferInitiation".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-142">Select the 'CustomerCreditTransferInitiation' definition.</span></span>  
8. <span data-ttu-id="cb1c4-143">Fare clic su Crea configurazione.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-143">Click Create configuration.</span></span>

## <a name="design-a-new-document-in-openxml-worksheet-format"></a><span data-ttu-id="cb1c4-144">Progettare un nuovo documento nel formato foglio di lavoro OPENXML</span><span class="sxs-lookup"><span data-stu-id="cb1c4-144">Design a new document in OPENXML worksheet format</span></span>
1. <span data-ttu-id="cb1c4-145">Nella struttura selezionare "Modello di pagamento\Report foglio di lavoro di esempio".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-145">In the tree, select 'Payment model\Sample worksheet report'.</span></span>
2. <span data-ttu-id="cb1c4-146">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-146">Click Designer.</span></span>
3. <span data-ttu-id="cb1c4-147">Nel Riquadro azioni fare clic su Importa.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-147">On the Action Pane, click Import.</span></span>
4. <span data-ttu-id="cb1c4-148">Fare clic su Importa da Excel.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-148">Click Import from Excel.</span></span>
5. <span data-ttu-id="cb1c4-149">Fare clic su Allegati.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-149">Click Attachments.</span></span>
    * <span data-ttu-id="cb1c4-150">Collegare il documento di Excel esistente come modello.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-150">Attach the existing Excel document as a template.</span></span>  
6. <span data-ttu-id="cb1c4-151">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-151">Click New.</span></span>
7. <span data-ttu-id="cb1c4-152">Fare clic su File.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-152">Click File.</span></span>
    * <span data-ttu-id="cb1c4-153">Puntare al file di Excel esistente.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-153">Point to the existing Excel file.</span></span>  
8. <span data-ttu-id="cb1c4-154">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-154">Close the page.</span></span>
9. <span data-ttu-id="cb1c4-155">Nel campo Modello immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-155">In the Template field, enter or select a value.</span></span>
    * <span data-ttu-id="cb1c4-156">Selezionare il file di Excel allegato da utilizzare come modello.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-156">Select the attached Excel file to be used as a template.</span></span>  
10. <span data-ttu-id="cb1c4-157">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-157">Click OK.</span></span>
    * <span data-ttu-id="cb1c4-158">I componenti del formato ER sono stati creati nel formato di progettazione basato sulla struttura del documento MS Excel di riferimento (intervalli denominati).</span><span class="sxs-lookup"><span data-stu-id="cb1c4-158">Note that ER format components have been created in the designing format based on the structure of the referring MS Excel document (named ranges).</span></span>  

## <a name="create-a-new-data-source-to-calculate-totals-by-currency-codes"></a><span data-ttu-id="cb1c4-159">Creare una nuova origine dati per calcolare i totali dei codici valuta</span><span class="sxs-lookup"><span data-stu-id="cb1c4-159">Create a new data source to calculate totals by currency codes</span></span>
1. <span data-ttu-id="cb1c4-160">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-160">Click the Mapping tab.</span></span>
2. <span data-ttu-id="cb1c4-161">Fare clic su Aggiungi radice per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-161">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="cb1c4-162">Nella struttura selezionare "Funzioni\Raggruppa per".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-162">In the tree, select 'Functions\Group by'.</span></span>
4. <span data-ttu-id="cb1c4-163">Nel campo Nome digitare "PaymentByCurrency".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-163">In the Name field, type 'PaymentByCurrency'.</span></span>
    * <span data-ttu-id="cb1c4-164">PaymentByCurrency</span><span class="sxs-lookup"><span data-stu-id="cb1c4-164">PaymentByCurrency</span></span>  
5. <span data-ttu-id="cb1c4-165">Fare clic su Modifica gruppo per.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-165">Click Edit group by.</span></span>
6. <span data-ttu-id="cb1c4-166">Nella struttura , espandere il "modello".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-166">In the tree, expand 'model'.</span></span>
7. <span data-ttu-id="cb1c4-167">Nella struttura selezionare "modello\Pagamenti".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-167">In the tree, select 'model\Payments'.</span></span>
8. <span data-ttu-id="cb1c4-168">Fare clic su Aggiungi campo a.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-168">Click Add field to.</span></span>
9. <span data-ttu-id="cb1c4-169">Fare clic su Informazioni da raggruppare.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-169">Click What to group.</span></span>
10. <span data-ttu-id="cb1c4-170">Nella struttura espandere "modello\Pagamenti".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-170">In the tree, expand 'model\Payments'.</span></span>
11. <span data-ttu-id="cb1c4-171">Nella struttura selezionare "modello\Pagamenti\Valuta".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-171">In the tree, select 'model\Payments\Currency'.</span></span>
12. <span data-ttu-id="cb1c4-172">Fare clic su Aggiungi campo a.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-172">Click Add field to.</span></span>
13. <span data-ttu-id="cb1c4-173">Fare clic su Campi raggruppati.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-173">Click Grouped fields.</span></span>
14. <span data-ttu-id="cb1c4-174">Nella struttura selezionare "modello\Pagamenti\Importo istruito(InstructedAmount)".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-174">In the tree, select 'model\Payments\Instructed Amount(InstructedAmount)'.</span></span>
15. <span data-ttu-id="cb1c4-175">Fare clic su Aggiungi campo a.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-175">Click Add field to.</span></span>
16. <span data-ttu-id="cb1c4-176">Fare clic su Campi di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-176">Click Aggregation fields.</span></span>
17. <span data-ttu-id="cb1c4-177">Selezionare un'opzione nel campo Metodo.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-177">In the Method field, select an option.</span></span>
    * <span data-ttu-id="cb1c4-178">Selezionare la funzione di aggregazione SOMMA.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-178">Select the SUM aggregation function.</span></span>  
18. <span data-ttu-id="cb1c4-179">Nel campo Nome digitare "TotalInstructuredAmount".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-179">In the Name field, type 'TotalInstructuredAmount'.</span></span>
    * <span data-ttu-id="cb1c4-180">TotalInstructuredAmount</span><span class="sxs-lookup"><span data-stu-id="cb1c4-180">TotalInstructuredAmount</span></span>  
19. <span data-ttu-id="cb1c4-181">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-181">Click Save.</span></span>
20. <span data-ttu-id="cb1c4-182">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-182">Close the page.</span></span>
21. <span data-ttu-id="cb1c4-183">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-183">Click OK.</span></span>

## <a name="map-format-components-to-data-sources"></a><span data-ttu-id="cb1c4-184">Eseguire il mapping dei componenti del formato alle origini dati</span><span class="sxs-lookup"><span data-stu-id="cb1c4-184">Map format components to data sources</span></span>
1. <span data-ttu-id="cb1c4-185">Nella struttura , espandere il "modello".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-185">In the tree, expand 'model'.</span></span>
2. <span data-ttu-id="cb1c4-186">Nella struttura espandere "modello\Pagamenti".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-186">In the tree, expand 'model\Payments'.</span></span>
3. <span data-ttu-id="cb1c4-187">Nella struttura espandere "modello\Pagamenti\Parte che inizia la transazione(InitiatingParty)".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-187">In the tree, expand 'model\Payments\Initiating Party(InitiatingParty)'.</span></span>
4. <span data-ttu-id="cb1c4-188">Nella struttura selezionare "modello\Pagamenti\Parte che inizia la transazione(InitiatingParty)\Nome".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-188">In the tree, select 'model\Payments\Initiating Party(InitiatingParty)\Name'.</span></span>
5. <span data-ttu-id="cb1c4-189">Nella struttura espandere 'Excel\ReportHeader'.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-189">In the tree, expand 'Excel\ReportHeader'.</span></span>
6. <span data-ttu-id="cb1c4-190">Nella struttura selezionare 'Excel\ReportHeader\CompanyName'.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-190">In the tree, select 'Excel\ReportHeader\CompanyName'.</span></span>
7. <span data-ttu-id="cb1c4-191">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-191">Click Bind.</span></span>
8. <span data-ttu-id="cb1c4-192">Nella struttura espandere "modello\Pagamenti\Creditore".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-192">In the tree, expand 'model\Payments\Creditor'.</span></span>
9. <span data-ttu-id="cb1c4-193">Nella struttura espandere "modello\Pagamenti\Creditore\Identificazione".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-193">In the tree, expand 'model\Payments\Creditor\Identification'.</span></span>
10. <span data-ttu-id="cb1c4-194">Nella struttura selezionare "modello\Pagamenti\Creditore\Identificazione\ID origine(SourceID)".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-194">In the tree, select 'model\Payments\Creditor\Identification\Source ID(SourceID)'.</span></span>
11. <span data-ttu-id="cb1c4-195">Nella struttura espandere 'Excel\PaymLines'.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-195">In the tree, expand 'Excel\PaymLines'.</span></span>
12. <span data-ttu-id="cb1c4-196">Nella struttura selezionare 'Excel\PaymLines\VendAccountName'.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-196">In the tree, select 'Excel\PaymLines\VendAccountName'.</span></span>
13. <span data-ttu-id="cb1c4-197">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-197">Click Bind.</span></span>
14. <span data-ttu-id="cb1c4-198">Nella struttura selezionare "modello\Pagamenti\Creditore\Nome".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-198">In the tree, select 'model\Payments\Creditor\Name'.</span></span>
15. <span data-ttu-id="cb1c4-199">Nella struttura selezionare 'Excel\PaymLines\VendName'.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-199">In the tree, select 'Excel\PaymLines\VendName'.</span></span>
16. <span data-ttu-id="cb1c4-200">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-200">Click Bind.</span></span>
17. <span data-ttu-id="cb1c4-201">Nella struttura espandere "modello\Pagamenti\Agente creditore(CreditorAgent)".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-201">In the tree, expand 'model\Payments\Creditor Agent(CreditorAgent)'.</span></span>
18. <span data-ttu-id="cb1c4-202">Nella struttura selezionare "modello\Pagamenti\Agente creditore(CreditorAgent)\Nome".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-202">In the tree, select 'model\Payments\Creditor Agent(CreditorAgent)\Name'.</span></span>
19. <span data-ttu-id="cb1c4-203">Nella struttura selezionare 'Excel\PaymLines\Banca'.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-203">In the tree, select 'Excel\PaymLines\Bank'.</span></span>
20. <span data-ttu-id="cb1c4-204">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-204">Click Bind.</span></span>
21. <span data-ttu-id="cb1c4-205">Nella struttura selezionare "modello\Pagamenti\Agente creditore(CreditorAgent)\Numero di registrazione(RoutingNumber)".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-205">In the tree, select 'model\Payments\Creditor Agent(CreditorAgent)\Routing Number(RoutingNumber)'.</span></span>
22. <span data-ttu-id="cb1c4-206">Nella struttura selezionare 'Excel\PaymLines\RoutingNumber'.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-206">In the tree, select 'Excel\PaymLines\RoutingNumber'.</span></span>
23. <span data-ttu-id="cb1c4-207">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-207">Click Bind.</span></span>
24. <span data-ttu-id="cb1c4-208">Nella struttura, espandere "modello\Pagamenti\Conto creditore(CreditorAccount)".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-208">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)'.</span></span>
25. <span data-ttu-id="cb1c4-209">Nella struttura, espandere "modello\Pagamenti\Conto creditore(CreditorAccount)\Identificazione".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-209">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)\Identification'.</span></span>
26. <span data-ttu-id="cb1c4-210">Nella struttura selezionare "modello\Pagamenti\Conto creditore(CreditorAccount)\Identificazione\Numero".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-210">In the tree, select 'model\Payments\Creditor Account(CreditorAccount)\Identification\Number'.</span></span>
27. <span data-ttu-id="cb1c4-211">Nella struttura selezionare 'Excel\PaymLines\AccountNumber'.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-211">In the tree, select 'Excel\PaymLines\AccountNumber'.</span></span>
28. <span data-ttu-id="cb1c4-212">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-212">Click Bind.</span></span>
29. <span data-ttu-id="cb1c4-213">Nella struttura selezionare "modello\Pagamenti\Importo istruito(InstructedAmount)".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-213">In the tree, select 'model\Payments\Instructed Amount(InstructedAmount)'.</span></span>
30. <span data-ttu-id="cb1c4-214">Nella struttura selezionare 'Excel\PaymLines\Debit'.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-214">In the tree, select 'Excel\PaymLines\Debit'.</span></span>
31. <span data-ttu-id="cb1c4-215">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-215">Click Bind.</span></span>
32. <span data-ttu-id="cb1c4-216">Nella struttura espandere "modello\Pagamenti\Creditore".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-216">In the tree, expand 'model\Payments\Creditor'.</span></span>
33. <span data-ttu-id="cb1c4-217">Nella struttura, espandere "modello\Pagamenti\Conto creditore(CreditorAccount)".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-217">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)'.</span></span>
34. <span data-ttu-id="cb1c4-218">Nella struttura espandere "modello\Pagamenti\Agente creditore(CreditorAgent)".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-218">In the tree, expand 'model\Payments\Creditor Agent(CreditorAgent)'.</span></span>
35. <span data-ttu-id="cb1c4-219">Nella struttura selezionare "modello\Pagamenti\Valuta".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-219">In the tree, select 'model\Payments\Currency'.</span></span>
36. <span data-ttu-id="cb1c4-220">Nella struttura selezionare 'Excel\PaymLines\Valuta'.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-220">In the tree, select 'Excel\PaymLines\Currency'.</span></span>
37. <span data-ttu-id="cb1c4-221">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-221">Click Bind.</span></span>
38. <span data-ttu-id="cb1c4-222">Nella struttura espandere "PaymentByCurrency".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-222">In the tree, expand 'PaymentByCurrency'.</span></span>
39. <span data-ttu-id="cb1c4-223">Nella struttura espandere "PaymentByCurrency\raggruppato".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-223">In the tree, expand 'PaymentByCurrency\grouped'.</span></span>
40. <span data-ttu-id="cb1c4-224">Nella struttura selezionare "PaymentByCurrency\raggruppato\Valuta".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-224">In the tree, select 'PaymentByCurrency\grouped\Currency'.</span></span>
41. <span data-ttu-id="cb1c4-225">Nella struttura espandere 'Excel\SummaryLines'.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-225">In the tree, expand 'Excel\SummaryLines'.</span></span>
42. <span data-ttu-id="cb1c4-226">Nella struttura selezionare 'Excel\SummaryLines\SummaryCurrency'.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-226">In the tree, select 'Excel\SummaryLines\SummaryCurrency'.</span></span>
43. <span data-ttu-id="cb1c4-227">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-227">Click Bind.</span></span>
44. <span data-ttu-id="cb1c4-228">Nella struttura espandere "PaymentByCurrency\aggregato".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-228">In the tree, expand 'PaymentByCurrency\aggregated'.</span></span>
45. <span data-ttu-id="cb1c4-229">Nella struttura selezionare "PaymentByCurrency\aggregato\TotalInstructuredAmount".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-229">In the tree, select 'PaymentByCurrency\aggregated\TotalInstructuredAmount'.</span></span>
46. <span data-ttu-id="cb1c4-230">Nella struttura selezionare 'Excel\SummaryLines\SummaryAmount'.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-230">In the tree, select 'Excel\SummaryLines\SummaryAmount'.</span></span>
47. <span data-ttu-id="cb1c4-231">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-231">Click Bind.</span></span>
48. <span data-ttu-id="cb1c4-232">Nella struttura selezionare "PaymentByCurrency".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-232">In the tree, select 'PaymentByCurrency'.</span></span>
49. <span data-ttu-id="cb1c4-233">Nella struttura selezionare 'Excel\SummaryLines'.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-233">In the tree, select 'Excel\SummaryLines'.</span></span>
50. <span data-ttu-id="cb1c4-234">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-234">Click Bind.</span></span>
51. <span data-ttu-id="cb1c4-235">Nella struttura selezionare "modello\Pagamenti".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-235">In the tree, select 'model\Payments'.</span></span>
52. <span data-ttu-id="cb1c4-236">Nella struttura selezionare 'Excel\PaymLines'.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-236">In the tree, select 'Excel\PaymLines'.</span></span>
53. <span data-ttu-id="cb1c4-237">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-237">Click Bind.</span></span>
54. <span data-ttu-id="cb1c4-238">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-238">Click Save.</span></span>
55. <span data-ttu-id="cb1c4-239">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-239">Close the page.</span></span>

## <a name="use-the-created-configuration-for-payments-processing"></a><span data-ttu-id="cb1c4-240">Utilizzare la configurazione creata per l'elaborazione di pagamenti</span><span class="sxs-lookup"><span data-stu-id="cb1c4-240">Use the created configuration for payments processing</span></span>
1. <span data-ttu-id="cb1c4-241">Fare clic su Cambia stato.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-241">Click Change status.</span></span>
2. <span data-ttu-id="cb1c4-242">Fare clic su Completa.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-242">Click Complete.</span></span>
3. <span data-ttu-id="cb1c4-243">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-243">Click OK.</span></span>
4. <span data-ttu-id="cb1c4-244">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-244">Close the page.</span></span>
5. <span data-ttu-id="cb1c4-245">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-245">Close the page.</span></span>
6. <span data-ttu-id="cb1c4-246">Andare a Contabilità fornitori > Impostazione pagamenti > Metodi di pagamento.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-246">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
7. <span data-ttu-id="cb1c4-247">Utilizzare il filtro rapido per filtrare il campo Metodo di pagamento in base a un valore di 'Electronic'.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-247">Use the Quick Filter to filter on the Method of payment field with a value of 'Electronic'.</span></span>
    * <span data-ttu-id="cb1c4-248">elettroniche</span><span class="sxs-lookup"><span data-stu-id="cb1c4-248">Electronic</span></span>  
8. <span data-ttu-id="cb1c4-249">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-249">Click Edit.</span></span>
9. <span data-ttu-id="cb1c4-250">Espandere la sezione Formati file.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-250">Expand the File formats section.</span></span>
10. <span data-ttu-id="cb1c4-251">Selezionare Sì nel campo Report elettronici generici.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-251">Select Yes in the Generic electronic reporting field.</span></span>
11. <span data-ttu-id="cb1c4-252">Nel campo Esporta configurazione formato immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-252">In the Export format configuration field, enter or select a value.</span></span>
    * <span data-ttu-id="cb1c4-253">Selezionare la configurazione "Report foglio di lavoro di esempio".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-253">Select the ‘Sample worksheet report’ configuration.</span></span>  
12. <span data-ttu-id="cb1c4-254">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-254">Click Save.</span></span>
13. <span data-ttu-id="cb1c4-255">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-255">Close the page.</span></span>

## <a name="use-the-created-configuration-for-testing-of-payment-journals-processing"></a><span data-ttu-id="cb1c4-256">Utilizzare la configurazione creata per testare l'elaborazione dei giornali di registrazione pagamenti</span><span class="sxs-lookup"><span data-stu-id="cb1c4-256">Use the created configuration for testing of payment journals processing</span></span>
1. <span data-ttu-id="cb1c4-257">Andare a Contabilità fornitori > Pagamenti > Giornale di registrazione pagamenti.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-257">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="cb1c4-258">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-258">Click New.</span></span>
    * <span data-ttu-id="cb1c4-259">Creare un nuovo giornale di registrazione pagamenti.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-259">Create a new payment journal.</span></span>  
3. <span data-ttu-id="cb1c4-260">Digitare 'VendPay' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-260">In the Name field, type 'VendPay'.</span></span>
    * <span data-ttu-id="cb1c4-261">VendPay</span><span class="sxs-lookup"><span data-stu-id="cb1c4-261">VendPay</span></span>  
4. <span data-ttu-id="cb1c4-262">Fare clic su Righe.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-262">Click Lines.</span></span>
5. <span data-ttu-id="cb1c4-263">Nel campo Conto specificare i valori "GB_SI_000001".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-263">In the Account field, specify the values 'GB_SI_000001'.</span></span>
    * <span data-ttu-id="cb1c4-264">GB_SI_000001</span><span class="sxs-lookup"><span data-stu-id="cb1c4-264">GB_SI_000001</span></span>  
6. <span data-ttu-id="cb1c4-265">Impostare Dare su "1000".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-265">Set Debit to '1000'.</span></span>
7. <span data-ttu-id="cb1c4-266">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-266">Click New.</span></span>
8. <span data-ttu-id="cb1c4-267">Nel campo Conto specificare i valori "GB_SI_000005".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-267">In the Account field, specify the values 'GB_SI_000005'.</span></span>
    * <span data-ttu-id="cb1c4-268">GB_SI_000005</span><span class="sxs-lookup"><span data-stu-id="cb1c4-268">GB_SI_000005</span></span>  
9. <span data-ttu-id="cb1c4-269">Impostare Dare su "2000".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-269">Set Debit to '2000'.</span></span>
10. <span data-ttu-id="cb1c4-270">Digitare "EUR" nel campo Valuta.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-270">In the Currency field, type 'EUR'.</span></span>
    * <span data-ttu-id="cb1c4-271">EUR</span><span class="sxs-lookup"><span data-stu-id="cb1c4-271">EUR</span></span>  
11. <span data-ttu-id="cb1c4-272">Nel campo Conto di contropartita specificare i valori "GBSI OPER".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-272">In the Offset account field, specify the values 'GBSI OPER'.</span></span>
    * <span data-ttu-id="cb1c4-273">GBSI OPER</span><span class="sxs-lookup"><span data-stu-id="cb1c4-273">GBSI OPER</span></span>  
12. <span data-ttu-id="cb1c4-274">Digitare "Elettronico" nel campo Metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-274">In the Method of payment field, type 'Electronic'.</span></span>
    * <span data-ttu-id="cb1c4-275">elettroniche</span><span class="sxs-lookup"><span data-stu-id="cb1c4-275">Electronic</span></span>  
13. <span data-ttu-id="cb1c4-276">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-276">Click Save.</span></span>
14. <span data-ttu-id="cb1c4-277">Fare clic su Genera pagamenti.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-277">Click Generate payments.</span></span>
15. <span data-ttu-id="cb1c4-278">Digitare "Elettronico" nel campo Metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-278">In the Method of payment field, type 'Electronic'.</span></span>
    * <span data-ttu-id="cb1c4-279">elettroniche</span><span class="sxs-lookup"><span data-stu-id="cb1c4-279">Electronic</span></span>  
16. <span data-ttu-id="cb1c4-280">Digitare 'Payments' nel campo Nome file.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-280">In the File name field, type 'Payments'.</span></span>
    * <span data-ttu-id="cb1c4-281">Ad esempio, digitare Pagamenti.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-281">For example, type Payments.</span></span>  
17. <span data-ttu-id="cb1c4-282">Nel campo Conto bancario digitare "GBSI OPER".</span><span class="sxs-lookup"><span data-stu-id="cb1c4-282">In the Bank account field, type 'GBSI OPER'.</span></span>
    * <span data-ttu-id="cb1c4-283">GBSI OPER</span><span class="sxs-lookup"><span data-stu-id="cb1c4-283">GBSI OPER</span></span>  
18. <span data-ttu-id="cb1c4-284">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-284">Click OK.</span></span>
19. <span data-ttu-id="cb1c4-285">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-285">Click OK.</span></span>
    * <span data-ttu-id="cb1c4-286">Verificare il foglio di lavoro creato, inclusi i dettagli delle righe di pagamento, nonché i totali per ciascun codice valuta utilizzato nel messaggio di pagamento.</span><span class="sxs-lookup"><span data-stu-id="cb1c4-286">Review the created worksheet, including details of payment lines as well as totals for each currency code used in this payment message.</span></span>  


