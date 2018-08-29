--- 
title: Progettare le configurazioni di ER per generare report in formato OpenXML
description: "I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare una nuova configurazione per la creazione di report elettronici (ER) che contiene un modello per la generazione di documenti elettronici in formato OPENXML."
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
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: b42cfe36c57a9526e585bbad0fcd31ff60b90397
ms.contentlocale: it-it
ms.lasthandoff: 08/09/2018

---
# <a name="design-er-configurations-to-generate-reports-in-openxml-format"></a><span data-ttu-id="0f0f0-103">Progettare le configurazioni di ER per generare report in formato OpenXML</span><span class="sxs-lookup"><span data-stu-id="0f0f0-103">Design ER configurations to generate reports in OpenXML format</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0f0f0-104">I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare una nuova configurazione per la creazione di report elettronici (ER) che contiene un modello per la generazione di documenti elettronici in formato OPENXML.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a template for generating electronic documents in OPENXML format.</span></span> <span data-ttu-id="0f0f0-105">La configurazione verrà utilizzata per elaborare i pagamenti fornitore.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-105">This configuration will be used for processing vendor payments.</span></span>



<span data-ttu-id="0f0f0-106">In questo esempio verrà creata una configurazione per la società di esempio Litware, Inc. Queste operazioni possono essere eseguite nella società GBSI.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in GBSI company.</span></span>



<span data-ttu-id="0f0f0-107">Per completare questi passaggi, è necessario completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-107">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span> <span data-ttu-id="0f0f0-108">È inoltre necessario scaricare e salvare il file di Microsoft Excel [Modello di Report di pagamento](https://go.microsoft.com/fwlink/?linkid=862266).</span><span class="sxs-lookup"><span data-stu-id="0f0f0-108">You must also download and save the Microsoft Excel file, [Template of Payment Report](https://go.microsoft.com/fwlink/?linkid=862266).</span></span> 

## <a name="upload-the-payments-data-model-configuration"></a><span data-ttu-id="0f0f0-109">Caricare la configurazione del modello dati Pagamenti</span><span class="sxs-lookup"><span data-stu-id="0f0f0-109">Upload the Payments data model configuration</span></span>
1. <span data-ttu-id="0f0f0-110">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="0f0f0-111">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="0f0f0-112">Selezionare il provider di configurazione per la società di esempio Litware, Inc. Se il provider di configurazione non viene visualizzato, è necessario innanzitutto completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-112">Select the configuration provider for sample company, Litware, Inc. If you don’t see this configuration provider, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>  
3. <span data-ttu-id="0f0f0-113">Fare clic su Imposta attivo.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-113">Click Set active.</span></span>
4. <span data-ttu-id="0f0f0-114">Fare clic su Archivi.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-114">Click Repositories.</span></span>
    * <span data-ttu-id="0f0f0-115">Selezionare un archivio per il tipo Risorse Operations, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-115">Select a repository for the Operations Resources type, if available.</span></span> <span data-ttu-id="0f0f0-116">Se è disponibile, ignorare i passaggi seguenti che riguardano la creazione di un nuovo archivio.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-116">If its available, skip the following steps about creating a new repository.</span></span>  
5. <span data-ttu-id="0f0f0-117">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-117">Click Add to open the drop dialog.</span></span>
6. <span data-ttu-id="0f0f0-118">Nel campo Tipo di archivio di configurazioni immettere 'Risorse operative'.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-118">In the Configuration repository type field, enter 'Operations resources'.</span></span>
7. <span data-ttu-id="0f0f0-119">Fare clic su Crea archivio.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-119">Click Create repository.</span></span>
8. <span data-ttu-id="0f0f0-120">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-120">Click OK.</span></span>
9. <span data-ttu-id="0f0f0-121">Fare clic su Apri.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-121">Click Open.</span></span>
10. <span data-ttu-id="0f0f0-122">Nella struttura selezionare "Modello di pagamento".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-122">In the tree, select 'Payment model'.</span></span>
11. <span data-ttu-id="0f0f0-123">Fare clic su Importa.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-123">Click Import.</span></span>
    * <span data-ttu-id="0f0f0-124">Importare questo modello dati.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-124">Import this data model.</span></span> <span data-ttu-id="0f0f0-125">Verrà utilizzato come origine dati in nuova configurazione del formato.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-125">It will be used as a data source in a new format configuration.</span></span> <span data-ttu-id="0f0f0-126">Ignorare questo passaggio se la configurazione è già stata importata.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-126">Skip this step if this configuration has been already imported.</span></span>  
12. <span data-ttu-id="0f0f0-127">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-127">Click Yes.</span></span>
13. <span data-ttu-id="0f0f0-128">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-128">Close the page.</span></span>
14. <span data-ttu-id="0f0f0-129">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-129">Close the page.</span></span>

## <a name="create-a-new-format-configuration"></a><span data-ttu-id="0f0f0-130">Creare una nuova configurazione di formato</span><span class="sxs-lookup"><span data-stu-id="0f0f0-130">Create a new format configuration</span></span>
1. <span data-ttu-id="0f0f0-131">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-131">Click Reporting configurations.</span></span>
2. <span data-ttu-id="0f0f0-132">Nella struttura selezionare "Modello di pagamento".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-132">In the tree, select 'Payment model'.</span></span>
3. <span data-ttu-id="0f0f0-133">Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .</span><span class="sxs-lookup"><span data-stu-id="0f0f0-133">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="0f0f0-134">Nel campo Nuovo immettere "Formato in base al modello dati PaymentModel".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-134">In the New field, enter 'Format based on data model PaymentModel'.</span></span>
    * <span data-ttu-id="0f0f0-135">Creare un formato basato sul modello dati PaymentModel.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-135">Create a format that is based on the PaymentModel data model.</span></span>  
5. <span data-ttu-id="0f0f0-136">Nel campo Nome digitare "Report foglio di lavoro di esempio".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-136">In the Name field, type 'Sample worksheet report'.</span></span>
    * <span data-ttu-id="0f0f0-137">Report foglio di lavoro di esempio</span><span class="sxs-lookup"><span data-stu-id="0f0f0-137">Sample worksheet report</span></span>  
6. <span data-ttu-id="0f0f0-138">Nel campo Descrizione immettere “Report foglio di lavoro per i pagamenti dei fornitori".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-138">In the Description field, type 'Sample worksheet report for vendors’ payments'.</span></span>
    * <span data-ttu-id="0f0f0-139">Report foglio di lavoro per i pagamenti dei fornitori.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-139">Sample worksheet report for vendors’ payments.</span></span>  
7. <span data-ttu-id="0f0f0-140">Nel campo Definizione modello dati immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-140">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="0f0f0-141">Selezionare la definizione "CustomerCreditTransferInitiation".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-141">Select the 'CustomerCreditTransferInitiation' definition.</span></span>  
8. <span data-ttu-id="0f0f0-142">Fare clic su Crea configurazione.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-142">Click Create configuration.</span></span>

## <a name="design-a-new-document-in-openxml-worksheet-format"></a><span data-ttu-id="0f0f0-143">Progettare un nuovo documento nel formato foglio di lavoro OPENXML</span><span class="sxs-lookup"><span data-stu-id="0f0f0-143">Design a new document in OPENXML worksheet format</span></span>
1. <span data-ttu-id="0f0f0-144">Nella struttura selezionare "Modello di pagamento\Report foglio di lavoro di esempio".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-144">In the tree, select 'Payment model\Sample worksheet report'.</span></span>
2. <span data-ttu-id="0f0f0-145">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-145">Click Designer.</span></span>
3. <span data-ttu-id="0f0f0-146">Nel Riquadro azioni fare clic su Importa.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-146">On the Action Pane, click Import.</span></span>
4. <span data-ttu-id="0f0f0-147">Fare clic su Importa da Excel.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-147">Click Import from Excel.</span></span>
5. <span data-ttu-id="0f0f0-148">Fare clic su Allegati.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-148">Click Attachments.</span></span>
    * <span data-ttu-id="0f0f0-149">Collegare il documento di Excel esistente come modello.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-149">Attach the existing Excel document as a template.</span></span>  
6. <span data-ttu-id="0f0f0-150">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-150">Click New.</span></span>
7. <span data-ttu-id="0f0f0-151">Fare clic su File.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-151">Click File.</span></span>
    * <span data-ttu-id="0f0f0-152">Puntare al file di Excel esistente.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-152">Point to the existing Excel file.</span></span>  
8. <span data-ttu-id="0f0f0-153">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-153">Close the page.</span></span>
9. <span data-ttu-id="0f0f0-154">Nel campo Modello immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-154">In the Template field, enter or select a value.</span></span>
    * <span data-ttu-id="0f0f0-155">Selezionare il file di Excel allegato da utilizzare come modello.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-155">Select the attached Excel file to be used as a template.</span></span>  
10. <span data-ttu-id="0f0f0-156">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-156">Click OK.</span></span>
    * <span data-ttu-id="0f0f0-157">I componenti del formato ER sono stati creati nel formato di progettazione basato sulla struttura del documento MS Excel di riferimento (intervalli denominati).</span><span class="sxs-lookup"><span data-stu-id="0f0f0-157">Note that ER format components have been created in the designing format based on the structure of the referring MS Excel document (named ranges).</span></span>  

## <a name="create-a-new-data-source-to-calculate-totals-by-currency-codes"></a><span data-ttu-id="0f0f0-158">Creare una nuova origine dati per calcolare i totali dei codici valuta</span><span class="sxs-lookup"><span data-stu-id="0f0f0-158">Create a new data source to calculate totals by currency codes</span></span>
1. <span data-ttu-id="0f0f0-159">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-159">Click the Mapping tab.</span></span>
2. <span data-ttu-id="0f0f0-160">Fare clic su Aggiungi radice per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-160">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="0f0f0-161">Nella struttura selezionare "Funzioni\Raggruppa per".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-161">In the tree, select 'Functions\Group by'.</span></span>
4. <span data-ttu-id="0f0f0-162">Nel campo Nome digitare "PaymentByCurrency".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-162">In the Name field, type 'PaymentByCurrency'.</span></span>
    * <span data-ttu-id="0f0f0-163">PaymentByCurrency</span><span class="sxs-lookup"><span data-stu-id="0f0f0-163">PaymentByCurrency</span></span>  
5. <span data-ttu-id="0f0f0-164">Fare clic su Modifica gruppo per.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-164">Click Edit group by.</span></span>
6. <span data-ttu-id="0f0f0-165">Nella struttura , espandere il "modello".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-165">In the tree, expand 'model'.</span></span>
7. <span data-ttu-id="0f0f0-166">Nella struttura selezionare "modello\Pagamenti".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-166">In the tree, select 'model\Payments'.</span></span>
8. <span data-ttu-id="0f0f0-167">Fare clic su Aggiungi campo a.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-167">Click Add field to.</span></span>
9. <span data-ttu-id="0f0f0-168">Fare clic su Informazioni da raggruppare.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-168">Click What to group.</span></span>
10. <span data-ttu-id="0f0f0-169">Nella struttura espandere "modello\Pagamenti".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-169">In the tree, expand 'model\Payments'.</span></span>
11. <span data-ttu-id="0f0f0-170">Nella struttura selezionare "modello\Pagamenti\Valuta".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-170">In the tree, select 'model\Payments\Currency'.</span></span>
12. <span data-ttu-id="0f0f0-171">Fare clic su Aggiungi campo a.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-171">Click Add field to.</span></span>
13. <span data-ttu-id="0f0f0-172">Fare clic su Campi raggruppati.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-172">Click Grouped fields.</span></span>
14. <span data-ttu-id="0f0f0-173">Nella struttura selezionare "modello\Pagamenti\Importo istruito(InstructedAmount)".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-173">In the tree, select 'model\Payments\Instructed Amount(InstructedAmount)'.</span></span>
15. <span data-ttu-id="0f0f0-174">Fare clic su Aggiungi campo a.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-174">Click Add field to.</span></span>
16. <span data-ttu-id="0f0f0-175">Fare clic su Campi di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-175">Click Aggregation fields.</span></span>
17. <span data-ttu-id="0f0f0-176">Selezionare un'opzione nel campo Metodo.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-176">In the Method field, select an option.</span></span>
    * <span data-ttu-id="0f0f0-177">Selezionare la funzione di aggregazione SOMMA.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-177">Select the SUM aggregation function.</span></span>  
18. <span data-ttu-id="0f0f0-178">Nel campo Nome digitare "TotalInstructuredAmount".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-178">In the Name field, type 'TotalInstructuredAmount'.</span></span>
    * <span data-ttu-id="0f0f0-179">TotalInstructuredAmount</span><span class="sxs-lookup"><span data-stu-id="0f0f0-179">TotalInstructuredAmount</span></span>  
19. <span data-ttu-id="0f0f0-180">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-180">Click Save.</span></span>
20. <span data-ttu-id="0f0f0-181">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-181">Close the page.</span></span>
21. <span data-ttu-id="0f0f0-182">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-182">Click OK.</span></span>

## <a name="map-format-components-to-data-sources"></a><span data-ttu-id="0f0f0-183">Eseguire il mapping dei componenti del formato alle origini dati</span><span class="sxs-lookup"><span data-stu-id="0f0f0-183">Map format components to data sources</span></span>
1. <span data-ttu-id="0f0f0-184">Nella struttura , espandere il "modello".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-184">In the tree, expand 'model'.</span></span>
2. <span data-ttu-id="0f0f0-185">Nella struttura espandere "modello\Pagamenti".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-185">In the tree, expand 'model\Payments'.</span></span>
3. <span data-ttu-id="0f0f0-186">Nella struttura espandere "modello\Pagamenti\Parte che inizia la transazione(InitiatingParty)".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-186">In the tree, expand 'model\Payments\Initiating Party(InitiatingParty)'.</span></span>
4. <span data-ttu-id="0f0f0-187">Nella struttura selezionare "modello\Pagamenti\Parte che inizia la transazione(InitiatingParty)\Nome".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-187">In the tree, select 'model\Payments\Initiating Party(InitiatingParty)\Name'.</span></span>
5. <span data-ttu-id="0f0f0-188">Nella struttura espandere 'Excel\ReportHeader'.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-188">In the tree, expand 'Excel\ReportHeader'.</span></span>
6. <span data-ttu-id="0f0f0-189">Nella struttura selezionare 'Excel\ReportHeader\CompanyName'.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-189">In the tree, select 'Excel\ReportHeader\CompanyName'.</span></span>
7. <span data-ttu-id="0f0f0-190">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-190">Click Bind.</span></span>
8. <span data-ttu-id="0f0f0-191">Nella struttura espandere "modello\Pagamenti\Creditore".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-191">In the tree, expand 'model\Payments\Creditor'.</span></span>
9. <span data-ttu-id="0f0f0-192">Nella struttura espandere "modello\Pagamenti\Creditore\Identificazione".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-192">In the tree, expand 'model\Payments\Creditor\Identification'.</span></span>
10. <span data-ttu-id="0f0f0-193">Nella struttura selezionare "modello\Pagamenti\Creditore\Identificazione\ID origine(SourceID)".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-193">In the tree, select 'model\Payments\Creditor\Identification\Source ID(SourceID)'.</span></span>
11. <span data-ttu-id="0f0f0-194">Nella struttura espandere 'Excel\PaymLines'.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-194">In the tree, expand 'Excel\PaymLines'.</span></span>
12. <span data-ttu-id="0f0f0-195">Nella struttura selezionare 'Excel\PaymLines\VendAccountName'.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-195">In the tree, select 'Excel\PaymLines\VendAccountName'.</span></span>
13. <span data-ttu-id="0f0f0-196">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-196">Click Bind.</span></span>
14. <span data-ttu-id="0f0f0-197">Nella struttura selezionare "modello\Pagamenti\Creditore\Nome".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-197">In the tree, select 'model\Payments\Creditor\Name'.</span></span>
15. <span data-ttu-id="0f0f0-198">Nella struttura selezionare 'Excel\PaymLines\VendName'.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-198">In the tree, select 'Excel\PaymLines\VendName'.</span></span>
16. <span data-ttu-id="0f0f0-199">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-199">Click Bind.</span></span>
17. <span data-ttu-id="0f0f0-200">Nella struttura espandere "modello\Pagamenti\Agente creditore(CreditorAgent)".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-200">In the tree, expand 'model\Payments\Creditor Agent(CreditorAgent)'.</span></span>
18. <span data-ttu-id="0f0f0-201">Nella struttura selezionare "modello\Pagamenti\Agente creditore(CreditorAgent)\Nome".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-201">In the tree, select 'model\Payments\Creditor Agent(CreditorAgent)\Name'.</span></span>
19. <span data-ttu-id="0f0f0-202">Nella struttura selezionare 'Excel\PaymLines\Banca'.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-202">In the tree, select 'Excel\PaymLines\Bank'.</span></span>
20. <span data-ttu-id="0f0f0-203">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-203">Click Bind.</span></span>
21. <span data-ttu-id="0f0f0-204">Nella struttura selezionare "modello\Pagamenti\Agente creditore(CreditorAgent)\Numero di registrazione(RoutingNumber)".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-204">In the tree, select 'model\Payments\Creditor Agent(CreditorAgent)\Routing Number(RoutingNumber)'.</span></span>
22. <span data-ttu-id="0f0f0-205">Nella struttura selezionare 'Excel\PaymLines\RoutingNumber'.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-205">In the tree, select 'Excel\PaymLines\RoutingNumber'.</span></span>
23. <span data-ttu-id="0f0f0-206">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-206">Click Bind.</span></span>
24. <span data-ttu-id="0f0f0-207">Nella struttura, espandere "modello\Pagamenti\Conto creditore(CreditorAccount)".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-207">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)'.</span></span>
25. <span data-ttu-id="0f0f0-208">Nella struttura, espandere "modello\Pagamenti\Conto creditore(CreditorAccount)\Identificazione".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-208">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)\Identification'.</span></span>
26. <span data-ttu-id="0f0f0-209">Nella struttura selezionare "modello\Pagamenti\Conto creditore(CreditorAccount)\Identificazione\Numero".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-209">In the tree, select 'model\Payments\Creditor Account(CreditorAccount)\Identification\Number'.</span></span>
27. <span data-ttu-id="0f0f0-210">Nella struttura selezionare 'Excel\PaymLines\AccountNumber'.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-210">In the tree, select 'Excel\PaymLines\AccountNumber'.</span></span>
28. <span data-ttu-id="0f0f0-211">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-211">Click Bind.</span></span>
29. <span data-ttu-id="0f0f0-212">Nella struttura selezionare "modello\Pagamenti\Importo istruito(InstructedAmount)".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-212">In the tree, select 'model\Payments\Instructed Amount(InstructedAmount)'.</span></span>
30. <span data-ttu-id="0f0f0-213">Nella struttura selezionare 'Excel\PaymLines\Debit'.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-213">In the tree, select 'Excel\PaymLines\Debit'.</span></span>
31. <span data-ttu-id="0f0f0-214">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-214">Click Bind.</span></span>
32. <span data-ttu-id="0f0f0-215">Nella struttura espandere "modello\Pagamenti\Creditore".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-215">In the tree, expand 'model\Payments\Creditor'.</span></span>
33. <span data-ttu-id="0f0f0-216">Nella struttura, espandere "modello\Pagamenti\Conto creditore(CreditorAccount)".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-216">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)'.</span></span>
34. <span data-ttu-id="0f0f0-217">Nella struttura espandere "modello\Pagamenti\Agente creditore(CreditorAgent)".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-217">In the tree, expand 'model\Payments\Creditor Agent(CreditorAgent)'.</span></span>
35. <span data-ttu-id="0f0f0-218">Nella struttura selezionare "modello\Pagamenti\Valuta".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-218">In the tree, select 'model\Payments\Currency'.</span></span>
36. <span data-ttu-id="0f0f0-219">Nella struttura selezionare 'Excel\PaymLines\Valuta'.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-219">In the tree, select 'Excel\PaymLines\Currency'.</span></span>
37. <span data-ttu-id="0f0f0-220">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-220">Click Bind.</span></span>
38. <span data-ttu-id="0f0f0-221">Nella struttura espandere "PaymentByCurrency".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-221">In the tree, expand 'PaymentByCurrency'.</span></span>
39. <span data-ttu-id="0f0f0-222">Nella struttura espandere "PaymentByCurrency\raggruppato".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-222">In the tree, expand 'PaymentByCurrency\grouped'.</span></span>
40. <span data-ttu-id="0f0f0-223">Nella struttura selezionare "PaymentByCurrency\raggruppato\Valuta".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-223">In the tree, select 'PaymentByCurrency\grouped\Currency'.</span></span>
41. <span data-ttu-id="0f0f0-224">Nella struttura espandere 'Excel\SummaryLines'.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-224">In the tree, expand 'Excel\SummaryLines'.</span></span>
42. <span data-ttu-id="0f0f0-225">Nella struttura selezionare 'Excel\SummaryLines\SummaryCurrency'.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-225">In the tree, select 'Excel\SummaryLines\SummaryCurrency'.</span></span>
43. <span data-ttu-id="0f0f0-226">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-226">Click Bind.</span></span>
44. <span data-ttu-id="0f0f0-227">Nella struttura espandere "PaymentByCurrency\aggregato".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-227">In the tree, expand 'PaymentByCurrency\aggregated'.</span></span>
45. <span data-ttu-id="0f0f0-228">Nella struttura selezionare "PaymentByCurrency\aggregato\TotalInstructuredAmount".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-228">In the tree, select 'PaymentByCurrency\aggregated\TotalInstructuredAmount'.</span></span>
46. <span data-ttu-id="0f0f0-229">Nella struttura selezionare 'Excel\SummaryLines\SummaryAmount'.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-229">In the tree, select 'Excel\SummaryLines\SummaryAmount'.</span></span>
47. <span data-ttu-id="0f0f0-230">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-230">Click Bind.</span></span>
48. <span data-ttu-id="0f0f0-231">Nella struttura selezionare "PaymentByCurrency".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-231">In the tree, select 'PaymentByCurrency'.</span></span>
49. <span data-ttu-id="0f0f0-232">Nella struttura selezionare 'Excel\SummaryLines'.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-232">In the tree, select 'Excel\SummaryLines'.</span></span>
50. <span data-ttu-id="0f0f0-233">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-233">Click Bind.</span></span>
51. <span data-ttu-id="0f0f0-234">Nella struttura selezionare "modello\Pagamenti".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-234">In the tree, select 'model\Payments'.</span></span>
52. <span data-ttu-id="0f0f0-235">Nella struttura selezionare 'Excel\PaymLines'.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-235">In the tree, select 'Excel\PaymLines'.</span></span>
53. <span data-ttu-id="0f0f0-236">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-236">Click Bind.</span></span>
54. <span data-ttu-id="0f0f0-237">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-237">Click Save.</span></span>
55. <span data-ttu-id="0f0f0-238">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-238">Close the page.</span></span>

## <a name="use-the-created-configuration-for-payments-processing"></a><span data-ttu-id="0f0f0-239">Utilizzare la configurazione creata per l'elaborazione di pagamenti</span><span class="sxs-lookup"><span data-stu-id="0f0f0-239">Use the created configuration for payments processing</span></span>
1. <span data-ttu-id="0f0f0-240">Fare clic su Cambia stato.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-240">Click Change status.</span></span>
2. <span data-ttu-id="0f0f0-241">Fare clic su Completa.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-241">Click Complete.</span></span>
3. <span data-ttu-id="0f0f0-242">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-242">Click OK.</span></span>
4. <span data-ttu-id="0f0f0-243">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-243">Close the page.</span></span>
5. <span data-ttu-id="0f0f0-244">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-244">Close the page.</span></span>
6. <span data-ttu-id="0f0f0-245">Andare a Contabilità fornitori > Impostazione pagamenti > Metodi di pagamento.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-245">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
7. <span data-ttu-id="0f0f0-246">Utilizzare il filtro rapido per filtrare il campo Metodo di pagamento in base a un valore di 'Electronic'.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-246">Use the Quick Filter to filter on the Method of payment field with a value of 'Electronic'.</span></span>
    * <span data-ttu-id="0f0f0-247">elettroniche</span><span class="sxs-lookup"><span data-stu-id="0f0f0-247">Electronic</span></span>  
8. <span data-ttu-id="0f0f0-248">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-248">Click Edit.</span></span>
9. <span data-ttu-id="0f0f0-249">Espandere la sezione Formati file.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-249">Expand the File formats section.</span></span>
10. <span data-ttu-id="0f0f0-250">Selezionare Sì nel campo Report elettronici generici.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-250">Select Yes in the Generic electronic reporting field.</span></span>
11. <span data-ttu-id="0f0f0-251">Nel campo Esporta configurazione formato immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-251">In the Export format configuration field, enter or select a value.</span></span>
    * <span data-ttu-id="0f0f0-252">Selezionare la configurazione "Report foglio di lavoro di esempio".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-252">Select the ‘Sample worksheet report’ configuration.</span></span>  
12. <span data-ttu-id="0f0f0-253">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-253">Click Save.</span></span>
13. <span data-ttu-id="0f0f0-254">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-254">Close the page.</span></span>

## <a name="use-the-created-configuration-for-testing-of-payment-journals-processing"></a><span data-ttu-id="0f0f0-255">Utilizzare la configurazione creata per testare l'elaborazione dei giornali di registrazione pagamenti</span><span class="sxs-lookup"><span data-stu-id="0f0f0-255">Use the created configuration for testing of payment journals processing</span></span>
1. <span data-ttu-id="0f0f0-256">Andare a Contabilità fornitori > Pagamenti > Giornale di registrazione pagamenti.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-256">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="0f0f0-257">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-257">Click New.</span></span>
    * <span data-ttu-id="0f0f0-258">Creare un nuovo giornale di registrazione pagamenti.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-258">Create a new payment journal.</span></span>  
3. <span data-ttu-id="0f0f0-259">Digitare 'VendPay' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-259">In the Name field, type 'VendPay'.</span></span>
    * <span data-ttu-id="0f0f0-260">VendPay</span><span class="sxs-lookup"><span data-stu-id="0f0f0-260">VendPay</span></span>  
4. <span data-ttu-id="0f0f0-261">Fare clic su Righe.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-261">Click Lines.</span></span>
5. <span data-ttu-id="0f0f0-262">Nel campo Conto specificare i valori "GB_SI_000001".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-262">In the Account field, specify the values 'GB_SI_000001'.</span></span>
    * <span data-ttu-id="0f0f0-263">GB_SI_000001</span><span class="sxs-lookup"><span data-stu-id="0f0f0-263">GB_SI_000001</span></span>  
6. <span data-ttu-id="0f0f0-264">Impostare Dare su "1000".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-264">Set Debit to '1000'.</span></span>
7. <span data-ttu-id="0f0f0-265">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-265">Click New.</span></span>
8. <span data-ttu-id="0f0f0-266">Nel campo Conto specificare i valori "GB_SI_000005".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-266">In the Account field, specify the values 'GB_SI_000005'.</span></span>
    * <span data-ttu-id="0f0f0-267">GB_SI_000005</span><span class="sxs-lookup"><span data-stu-id="0f0f0-267">GB_SI_000005</span></span>  
9. <span data-ttu-id="0f0f0-268">Impostare Dare su "2000".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-268">Set Debit to '2000'.</span></span>
10. <span data-ttu-id="0f0f0-269">Digitare "EUR" nel campo Valuta.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-269">In the Currency field, type 'EUR'.</span></span>
    * <span data-ttu-id="0f0f0-270">EUR</span><span class="sxs-lookup"><span data-stu-id="0f0f0-270">EUR</span></span>  
11. <span data-ttu-id="0f0f0-271">Nel campo Conto di contropartita specificare i valori "GBSI OPER".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-271">In the Offset account field, specify the values 'GBSI OPER'.</span></span>
    * <span data-ttu-id="0f0f0-272">GBSI OPER</span><span class="sxs-lookup"><span data-stu-id="0f0f0-272">GBSI OPER</span></span>  
12. <span data-ttu-id="0f0f0-273">Digitare "Elettronico" nel campo Metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-273">In the Method of payment field, type 'Electronic'.</span></span>
    * <span data-ttu-id="0f0f0-274">elettroniche</span><span class="sxs-lookup"><span data-stu-id="0f0f0-274">Electronic</span></span>  
13. <span data-ttu-id="0f0f0-275">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-275">Click Save.</span></span>
14. <span data-ttu-id="0f0f0-276">Fare clic su Genera pagamenti.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-276">Click Generate payments.</span></span>
15. <span data-ttu-id="0f0f0-277">Digitare "Elettronico" nel campo Metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-277">In the Method of payment field, type 'Electronic'.</span></span>
    * <span data-ttu-id="0f0f0-278">elettroniche</span><span class="sxs-lookup"><span data-stu-id="0f0f0-278">Electronic</span></span>  
16. <span data-ttu-id="0f0f0-279">Digitare 'Payments' nel campo Nome file.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-279">In the File name field, type 'Payments'.</span></span>
    * <span data-ttu-id="0f0f0-280">Ad esempio, digitare Pagamenti.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-280">For example, type Payments.</span></span>  
17. <span data-ttu-id="0f0f0-281">Nel campo Conto bancario digitare "GBSI OPER".</span><span class="sxs-lookup"><span data-stu-id="0f0f0-281">In the Bank account field, type 'GBSI OPER'.</span></span>
    * <span data-ttu-id="0f0f0-282">GBSI OPER</span><span class="sxs-lookup"><span data-stu-id="0f0f0-282">GBSI OPER</span></span>  
18. <span data-ttu-id="0f0f0-283">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-283">Click OK.</span></span>
19. <span data-ttu-id="0f0f0-284">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-284">Click OK.</span></span>
    * <span data-ttu-id="0f0f0-285">Verificare il foglio di lavoro creato, inclusi i dettagli delle righe di pagamento, nonché i totali per ciascun codice valuta utilizzato nel messaggio di pagamento.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-285">Review the created worksheet, including details of payment lines as well as totals for each currency code used in this payment message.</span></span>  


