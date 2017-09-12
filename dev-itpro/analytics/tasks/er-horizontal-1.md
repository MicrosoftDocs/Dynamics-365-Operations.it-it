--- 
title: Progettare un formato per utilizzare gli intervalli espandibili orizzontalmente per aggiungere colonne in modo dinamico ai report di Excel per la creazione di report elettronici (ER)
description: "I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la generazione di report come file di fogli di lavoro (Excel) OPENXML in cui le colonne richieste possono essere create in modo dinamico come intervalli espandibili orizzontalmente."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: fdba6a68cd98b0ccbc4072f5c1124088ed9d814b
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="design-a-format-to-use-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports-for-electronic-reporting-er"></a><span data-ttu-id="dd9d8-103">Progettare un formato per utilizzare gli intervalli espandibili orizzontalmente per aggiungere colonne in modo dinamico ai report di Excel per la creazione di report elettronici (ER)</span><span class="sxs-lookup"><span data-stu-id="dd9d8-103">Design a format to use horizontally-expandable ranges to dynamically add columns in Excel reports for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="dd9d8-104">I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la generazione di report come file di fogli di lavoro (Excel) OPENXML in cui le colonne richieste possono essere create in modo dinamico come intervalli espandibili orizzontalmente.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to generate reports as OPENXML worksheets (Excel) files in which the required columns can be created dynamically as horizontally expandable ranges.</span></span> <span data-ttu-id="dd9d8-105">Questi passaggi possono essere eseguiti in qualsiasi società.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="dd9d8-106">Per effettuare queste operazioni, è necessario completare queste tre guide attività:</span><span class="sxs-lookup"><span data-stu-id="dd9d8-106">To complete these steps, you must first complete these three task guides:</span></span> 

<span data-ttu-id="dd9d8-107">"ER Creare un provider di configurazione e contrassegnarlo come attivo"</span><span class="sxs-lookup"><span data-stu-id="dd9d8-107">“ER Create a configuration provider and mark it as active”</span></span>

<span data-ttu-id="dd9d8-108">"ER Utilizzare le dimensioni finanziarie come origine dati (parte 1: progettare il modello dati)"</span><span class="sxs-lookup"><span data-stu-id="dd9d8-108">“ER Use financial dimensions as a data source (Part 1: Design data model)”</span></span>

<span data-ttu-id="dd9d8-109">"ER Utilizzare le dimensioni finanziarie come origine dati (parte 2: mapping del modello)"</span><span class="sxs-lookup"><span data-stu-id="dd9d8-109">“ER Use financial dimensions as a data source (Part 2: Model mapping)”</span></span>

<span data-ttu-id="dd9d8-110">È inoltre necessario scaricare e salvare una copia locale del modello con un report di esempio disponibile qui: http://msdynamics.blob.core.windows.net/media/2016/09/SampleFinDimWsReport.xlsx</span><span class="sxs-lookup"><span data-stu-id="dd9d8-110">You must also download and save a local copy of the template with a sample report found here: http://msdynamics.blob.core.windows.net/media/2016/09/SampleFinDimWsReport.xlsx</span></span>

<span data-ttu-id="dd9d8-111">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-111">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-new-report-configuration"></a><span data-ttu-id="dd9d8-112">Creare una nuova configurazione di report</span><span class="sxs-lookup"><span data-stu-id="dd9d8-112">Create a new report configuration</span></span>
1. <span data-ttu-id="dd9d8-113">Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-113">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="dd9d8-114">Nella struttura selezionare 'Modello di esempio dimensioni finanziarie'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-114">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="dd9d8-115">Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .</span><span class="sxs-lookup"><span data-stu-id="dd9d8-115">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="dd9d8-116">Nel campo Nuovo immettere 'Formato basato sul modello dati Modello di esempio dimensioni finanziarie'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-116">In the New field, enter 'Format based on data model Financial dimensions sample model'.</span></span>
    * <span data-ttu-id="dd9d8-117">Utilizzare il modello creato in anticipo come origine dati per il nuovo report.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-117">Use the model created in advance as the data source for your new report.</span></span>  
5. <span data-ttu-id="dd9d8-118">Nel campo nome digitare 'Report di esempio con intervalli espandibili orizzontalmente'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-118">In the Name field, type 'Sample report with horizontally expandable ranges'.</span></span>
    * <span data-ttu-id="dd9d8-119">Report di esempio con intervalli espandibili orizzontalmente</span><span class="sxs-lookup"><span data-stu-id="dd9d8-119">Sample report with horizontally expandable ranges</span></span>  
6. <span data-ttu-id="dd9d8-120">Nel campo Descrizione, digitare 'Creare l'output Excel con l'aggiunta dinamica di colonne'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-120">In the Description field, type 'To make Excel output with dynamically adding columns'.</span></span>
    * <span data-ttu-id="dd9d8-121">Creare l'output Excel con l'aggiunta dinamica di colonne</span><span class="sxs-lookup"><span data-stu-id="dd9d8-121">To make Excel output with dynamically adding columns</span></span>  
7. <span data-ttu-id="dd9d8-122">Selezionare Voce nel campo Definizione modello dati.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-122">In the Data model definition field, select Entry.</span></span>
8. <span data-ttu-id="dd9d8-123">Fare clic su Crea configurazione.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-123">Click Create configuration.</span></span>

## <a name="design-the-report-format"></a><span data-ttu-id="dd9d8-124">Progettare il formato del report</span><span class="sxs-lookup"><span data-stu-id="dd9d8-124">Design the report format</span></span>
1. <span data-ttu-id="dd9d8-125">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-125">Click Designer.</span></span>
2. <span data-ttu-id="dd9d8-126">Attivare l'interruttore 'Mostra dettagli'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-126">Turn on the ‘Show details’ toggle button.</span></span>
3. <span data-ttu-id="dd9d8-127">Nel Riquadro azioni fare clic su Importa.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-127">On the Action Pane, click Import.</span></span>
4. <span data-ttu-id="dd9d8-128">Fare clic su Importa da Excel.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-128">Click Import from Excel.</span></span>
5. <span data-ttu-id="dd9d8-129">Fare clic su Allegati.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-129">Click Attachments.</span></span>
    * <span data-ttu-id="dd9d8-130">Importare il modello di report.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-130">Import the report’s template.</span></span> <span data-ttu-id="dd9d8-131">Usare il file di Excel di utilizzo scaricato allo scopo.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-131">Use Excel file that you downloaded for that.</span></span>  
6. <span data-ttu-id="dd9d8-132">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-132">Click New.</span></span>
7. <span data-ttu-id="dd9d8-133">Fare clic su File.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-133">Click File.</span></span>
8. <span data-ttu-id="dd9d8-134">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-134">Close the page.</span></span>
9. <span data-ttu-id="dd9d8-135">Nel campo Modello immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-135">In the Template field, enter or select a value.</span></span>
    * <span data-ttu-id="dd9d8-136">Selezionare il modello scaricato.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-136">Select the downloaded template.</span></span>  
10. <span data-ttu-id="dd9d8-137">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-137">Click OK.</span></span>
    * <span data-ttu-id="dd9d8-138">Aggiungere un nuovo intervallo per creare in modo dinamico l'output di Excel con il numero di colonne selezionato (nel modulo di dialogo utente) per le dimensioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-138">Add a new range to dynamically create Excel output with as many columns as you selected (in the user dialog form) for financial dimensions.</span></span> <span data-ttu-id="dd9d8-139">Ogni cella per ciascuna colonna rappresenterà il nome di una singola dimensione finanziaria.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-139">Each cell for every column will represent a single financial dimension’s name.</span></span>  
11. <span data-ttu-id="dd9d8-140">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-140">Click Add to open the drop dialog.</span></span>
12. <span data-ttu-id="dd9d8-141">Nella struttura selezionare 'Excel\Intervallo'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-141">In the tree, select 'Excel\Range'.</span></span>
13. <span data-ttu-id="dd9d8-142">Nel campo Intervallo Excel, digitare 'DimNames'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-142">In the Excel range field, type 'DimNames'.</span></span>
    * <span data-ttu-id="dd9d8-143">DimNames</span><span class="sxs-lookup"><span data-stu-id="dd9d8-143">DimNames</span></span>  
14. <span data-ttu-id="dd9d8-144">Selezionare 'Orizzontale' nel campo Direzione replica.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-144">In the Replication direction field, select 'Horizontal'.</span></span>
15. <span data-ttu-id="dd9d8-145">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-145">Click OK.</span></span>
16. <span data-ttu-id="dd9d8-146">Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Intervallo<DimNames>: Orizzontale'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-146">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal'.</span></span>
17. <span data-ttu-id="dd9d8-147">Fare clic su Sposta su.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-147">Click Move up.</span></span>
18. <span data-ttu-id="dd9d8-148">Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Cella<DimNames>.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-148">In the tree, select 'Excel = "SampleFinDimWsReport"\Cell<DimNames>'.</span></span>
19. <span data-ttu-id="dd9d8-149">Fare clic su Taglia.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-149">Click Cut.</span></span>
20. <span data-ttu-id="dd9d8-150">Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Intervallo<DimNames>: Orizzontale'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-150">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal'.</span></span>
21. <span data-ttu-id="dd9d8-151">Fare clic su Incolla.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-151">Click Paste.</span></span>
22. <span data-ttu-id="dd9d8-152">Nella struttura espandere 'Excel = "SampleFinDimWsReport"\Intervallo<DimNames>: Orizzontale'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-152">In the tree, expand 'Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal'.</span></span>
23. <span data-ttu-id="dd9d8-153">Nella struttura espandere 'Excel = "SampleFinDimWsReport"\Intervallo<JournalLine>: Verticale'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-153">In the tree, expand 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical'.</span></span>
24. <span data-ttu-id="dd9d8-154">Nella struttura espandere 'Excel = "SampleFinDimWsReport"\Intervallo<JournalLine>: Verticale\Intervallo<TransactionLine>: Verticale'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-154">In the tree, expand 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical'.</span></span>
25. <span data-ttu-id="dd9d8-155">Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Intervallo<JournalLine>: Verticale\Intervallo<TransactionLine>: Verticale'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-155">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical'.</span></span>
    * <span data-ttu-id="dd9d8-156">Aggiungere un nuovo intervallo per creare in modo dinamico l'output di Excel con il numero di colonne selezionato (nel modulo di dialogo utente) per le dimensioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-156">Add a new range to dynamically create Excel output with as many columns as you selected (in the user dialog form) for financial dimensions.</span></span> <span data-ttu-id="dd9d8-157">Ogni cella per ciascuna colonna rappresenterà il valore di una singola dimensione finanziaria per ogni transazione nel report.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-157">Each cell for every column will represent a single financial dimension’s value for each reporting transaction.</span></span>  
26. <span data-ttu-id="dd9d8-158">Fare clic su Aggiungi intervallo.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-158">Click Add Range.</span></span>
27. <span data-ttu-id="dd9d8-159">Nel campo Intervallo Excel, digitare 'DimValues'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-159">In the Excel range field, type 'DimValues'.</span></span>
    * <span data-ttu-id="dd9d8-160">DimValues</span><span class="sxs-lookup"><span data-stu-id="dd9d8-160">DimValues</span></span>  
28. <span data-ttu-id="dd9d8-161">Selezionare 'Orizzontale' nel campo Direzione replica.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-161">In the Replication direction field, select 'Horizontal'.</span></span>
29. <span data-ttu-id="dd9d8-162">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-162">Click OK.</span></span>
30. <span data-ttu-id="dd9d8-163">Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Intervallo<JournalLine>: Verticale\Intervallo<TransactionLine>: Verticale\Cella<DimValues>'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-163">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<DimValues>'.</span></span>
31. <span data-ttu-id="dd9d8-164">Fare clic su Taglia.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-164">Click Cut.</span></span>
32. <span data-ttu-id="dd9d8-165">Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Intervallo<JournalLine>: Verticale\Intervallo<TransactionLine>: Verticale\Intervallo<DimValues>: Orizzontale'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-165">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal'.</span></span>
33. <span data-ttu-id="dd9d8-166">Fare clic su Incolla.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-166">Click Paste.</span></span>
34. <span data-ttu-id="dd9d8-167">Nella struttura espandere 'Excel = "SampleFinDimWsReport"\Intervallo<JournalLine>: Verticale\Intervallo<TransactionLine>: Verticale\Intervallo<DimValues>: Orizzontale'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-167">In the tree, expand 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal'.</span></span>

## <a name="map-format-elements-to-data-sources"></a><span data-ttu-id="dd9d8-168">Mappare gli elementi di formato alle origini dati</span><span class="sxs-lookup"><span data-stu-id="dd9d8-168">Map format elements to data sources</span></span>
1. <span data-ttu-id="dd9d8-169">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-169">Click the Mapping tab.</span></span>
2. <span data-ttu-id="dd9d8-170">Nella struttura, espandere 'modello: Modello dati Modello di esempio dimensioni finanziarie'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-170">In the tree, expand 'model: Data model Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="dd9d8-171">Nella struttura, espandere 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-171">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
4. <span data-ttu-id="dd9d8-172">Nella struttura, espandere 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-172">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
5. <span data-ttu-id="dd9d8-173">Nella struttura, espandere 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dati dimensioni: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-173">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
6. <span data-ttu-id="dd9d8-174">Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Intervallo<JournalLine>: Verticale\Intervallo<TransactionLine>: Verticale\Intervallo<DimValues>: Orizzontale\Cella<DimValues>'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-174">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal\Cell<DimValues>'.</span></span>
7. <span data-ttu-id="dd9d8-175">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dati dimensioni: Elenco di record\Codice: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-175">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String'.</span></span>
8. <span data-ttu-id="dd9d8-176">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-176">Click Bind.</span></span>
9. <span data-ttu-id="dd9d8-177">Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Intervallo<JournalLine>: Verticale\Intervallo<TransactionLine>: Verticale\Intervallo<DimValues>: Orizzontale'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-177">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal'.</span></span>
10. <span data-ttu-id="dd9d8-178">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dati dimensioni: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-178">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
11. <span data-ttu-id="dd9d8-179">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-179">Click Bind.</span></span>
12. <span data-ttu-id="dd9d8-180">Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Intervallo<JournalLine>: Verticale\Intervallo<TransactionLine>: Verticale\Cella<Credit>'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-180">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Credit>'.</span></span>
13. <span data-ttu-id="dd9d8-181">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Avere: Reale'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-181">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real'.</span></span>
14. <span data-ttu-id="dd9d8-182">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-182">Click Bind.</span></span>
15. <span data-ttu-id="dd9d8-183">Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Intervallo<JournalLine>: Verticale\Intervallo<TransactionLine>: Verticale\Cella<Debit>'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-183">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Debit>'.</span></span>
16. <span data-ttu-id="dd9d8-184">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dare: Reale'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-184">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real'.</span></span>
17. <span data-ttu-id="dd9d8-185">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-185">Click Bind.</span></span>
18. <span data-ttu-id="dd9d8-186">Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Intervallo<JournalLine>: Verticale\Intervallo<TransactionLine>: Verticale\Cella<Currency>'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-186">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Currency>'.</span></span>
19. <span data-ttu-id="dd9d8-187">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Valuta: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-187">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String'.</span></span>
20. <span data-ttu-id="dd9d8-188">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-188">Click Bind.</span></span>
21. <span data-ttu-id="dd9d8-189">Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Intervallo<JournalLine>: Verticale\Intervallo<TransactionLine>: Verticale\Cella<TransDate>'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-189">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransDate>'.</span></span>
22. <span data-ttu-id="dd9d8-190">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Data: Data'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-190">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date'.</span></span>
23. <span data-ttu-id="dd9d8-191">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-191">Click Bind.</span></span>
24. <span data-ttu-id="dd9d8-192">Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Intervallo<JournalLine>: Verticale\Intervallo<TransactionLine>: Verticale\Cella<TransVoucher>'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-192">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransVoucher>'.</span></span>
25. <span data-ttu-id="dd9d8-193">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Giustificativo: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-193">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String'.</span></span>
26. <span data-ttu-id="dd9d8-194">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-194">Click Bind.</span></span>
27. <span data-ttu-id="dd9d8-195">Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Intervallo<JournalLine>: Verticale\Intervallo<TransactionLine>: Verticale\Cella<TransBatch>'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-195">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransBatch>'.</span></span>
28. <span data-ttu-id="dd9d8-196">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Batch: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-196">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Batch: String'.</span></span>
29. <span data-ttu-id="dd9d8-197">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-197">Click Bind.</span></span>
30. <span data-ttu-id="dd9d8-198">Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Intervallo<JournalLine>: Verticale\Intervallo<TransactionLine>: Verticale'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-198">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical'.</span></span>
31. <span data-ttu-id="dd9d8-199">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-199">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
32. <span data-ttu-id="dd9d8-200">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-200">Click Bind.</span></span>
33. <span data-ttu-id="dd9d8-201">Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Intervallo<JournalLine>: Verticale\Cella<Batch>'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-201">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Cell<Batch>'.</span></span>
34. <span data-ttu-id="dd9d8-202">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Batch: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-202">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Batch: String'.</span></span>
35. <span data-ttu-id="dd9d8-203">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-203">Click Bind.</span></span>
36. <span data-ttu-id="dd9d8-204">Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Intervallo<JournalLine>: Verticale'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-204">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical'.</span></span>
37. <span data-ttu-id="dd9d8-205">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-205">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
38. <span data-ttu-id="dd9d8-206">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-206">Click Bind.</span></span>
39. <span data-ttu-id="dd9d8-207">Nella struttura, espandere 'modello: Modello dati Modello di esempio dimensioni finanziarie\Impostazione dimensioni: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-207">In the tree, expand 'model: Data model Financial dimensions sample model\Dimensions setting: Record list'.</span></span>
40. <span data-ttu-id="dd9d8-208">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Impostazione dimensioni: Elenco di record\Codice: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-208">In the tree, select 'model: Data model Financial dimensions sample model\Dimensions setting: Record list\Code: String'.</span></span>
41. <span data-ttu-id="dd9d8-209">Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Intervallo<DimNames>: Orizzontale\Cella<DimNames>'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-209">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal\Cell<DimNames>'.</span></span>
42. <span data-ttu-id="dd9d8-210">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-210">Click Bind.</span></span>
43. <span data-ttu-id="dd9d8-211">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Impostazione dimensioni: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-211">In the tree, select 'model: Data model Financial dimensions sample model\Dimensions setting: Record list'.</span></span>
44. <span data-ttu-id="dd9d8-212">Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Intervallo<DimNames>: Orizzontale'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-212">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal'.</span></span>
45. <span data-ttu-id="dd9d8-213">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-213">Click Bind.</span></span>
46. <span data-ttu-id="dd9d8-214">Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Cella<CompanyName>.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-214">In the tree, select 'Excel = "SampleFinDimWsReport"\Cell<CompanyName>'.</span></span>
47. <span data-ttu-id="dd9d8-215">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Società: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-215">In the tree, select 'model: Data model Financial dimensions sample model\Company: String'.</span></span>
48. <span data-ttu-id="dd9d8-216">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-216">Click Bind.</span></span>
49. <span data-ttu-id="dd9d8-217">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-217">Click Save.</span></span>
50. <span data-ttu-id="dd9d8-218">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="dd9d8-218">Close the page.</span></span>

