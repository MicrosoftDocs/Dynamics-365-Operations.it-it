---
title: Modificare i modelli e i mapping per generare documenti che contengono dati dell'applicazione
description: Questo argomento descrive come progettare le configurazioni di creazione di report per generare un documento elettronico e aggiornare i dati dell'applicazione. (Parte 2 - Generare documenti).
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 64bcf885fe2f5fca6b91589171b5e539eff2c3e5
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567094"
---
# <a name="modify-models-and-mappings-to-generate-documents-that-have-application-data"></a><span data-ttu-id="78bcd-104">Modificare i modelli e i mapping per generare documenti che contengono dati dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="78bcd-104">Modify models and mappings to generate documents that have application data</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="78bcd-105">Per completare i passaggi di questa procedura, è necessario completare la procedura "ER Generare documenti con l'aggiornamento dei dati dell'applicazione (Parte 2: Generare documenti)".</span><span class="sxs-lookup"><span data-stu-id="78bcd-105">To complete the steps in this procedure, you must first complete the procedure, "ER Generate documents with application data update (Part 2: Generate documents)".</span></span> 

<span data-ttu-id="78bcd-106">I passaggi di questa procedura descrivono come progettare le configurazioni ER per generare un documento elettronico e aggiornare i dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="78bcd-106">The steps in this procedure explain how to design Electronic reporting (ER) configurations to generate an electronic document and update application data.</span></span> <span data-ttu-id="78bcd-107">In questa procedura verranno modificate le configurazioni ER per iniziare a utilizzarle per generare i documenti elettronici e per aggiornare i dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="78bcd-107">In this procedure, you will modify the ER configurations to start using them to generate electronic documents and update application data.</span></span> <span data-ttu-id="78bcd-108">Questa procedura viene creata per utenti con il ruolo di amministratore di sistema o di sviluppatore di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="78bcd-108">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="78bcd-109">Tali passaggi possono essere completati mediante il set di dati DEMF.</span><span class="sxs-lookup"><span data-stu-id="78bcd-109">These steps can be completed using the DEMF dataset.</span></span>


## <a name="modify-data-model"></a><span data-ttu-id="78bcd-110">Modificare il modello dati</span><span class="sxs-lookup"><span data-stu-id="78bcd-110">Modify data model</span></span>
1. <span data-ttu-id="78bcd-111">Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.</span><span class="sxs-lookup"><span data-stu-id="78bcd-111">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="78bcd-112">Nella struttura selezionare "Intrastat (model)".</span><span class="sxs-lookup"><span data-stu-id="78bcd-112">In the tree, select 'Intrastat (model)'.</span></span>
    * <span data-ttu-id="78bcd-113">A questo punto verranno estese le modalità di utilizzo del modello dati.</span><span class="sxs-lookup"><span data-stu-id="78bcd-113">You will extend how you use the data model.</span></span> <span data-ttu-id="78bcd-114">Oltre a utilizzarlo come origine dati per generare il report Intrastat, il modello dati verrà utilizzato per raccogliere informazioni dettagliate sul processo di dichiarazione Intrastat.</span><span class="sxs-lookup"><span data-stu-id="78bcd-114">Besides using it as data source to generate the Intrastat report, the data model will be used to collect details about the Intrastat reporting process.</span></span> <span data-ttu-id="78bcd-115">I dettagli verranno utilizzati per aggiornare i dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="78bcd-115">The details will then be used to update application data.</span></span>   
3. <span data-ttu-id="78bcd-116">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="78bcd-116">Click Designer.</span></span>
4. <span data-ttu-id="78bcd-117">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="78bcd-117">Click New to open the drop dialog.</span></span>
5. <span data-ttu-id="78bcd-118">Nel campo Nuovo nodo come immettere 'Radice modello'.</span><span class="sxs-lookup"><span data-stu-id="78bcd-118">In the New node as a field, enter 'Model root'.</span></span>
6. <span data-ttu-id="78bcd-119">Nel campo Nome digitare "Per l'aggiornamento dei dati dell'applicazione".</span><span class="sxs-lookup"><span data-stu-id="78bcd-119">In the Name field, type 'For application data update'.</span></span>
    * <span data-ttu-id="78bcd-120">Per l'aggiornamento dei dati dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="78bcd-120">For application data update</span></span>  
7. <span data-ttu-id="78bcd-121">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="78bcd-121">Click Add.</span></span>
8. <span data-ttu-id="78bcd-122">Nella struttura selezionare "For application data update".</span><span class="sxs-lookup"><span data-stu-id="78bcd-122">In the tree, select 'For application data update'.</span></span>
    * <span data-ttu-id="78bcd-123">Il nuovo elemento radice viene aggiunto per specificare il flusso di dati per lo spostamento dei dati dal report Intrastat (utilizzato come origine dati) alle tabelle dell'applicazione (destinazione dell'aggiornamento).</span><span class="sxs-lookup"><span data-stu-id="78bcd-123">This new root item is added to specify the data flow for moving data from the Intrastat report (used as a data source) to the application tables (the update destination).</span></span> <span data-ttu-id="78bcd-124">Si noti che è necessario utilizzare elementi radice diversi per ottenere i dati registrati nel documento in uscita e per ottenere i dati del documento utilizzato per aggiornare i dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="78bcd-124">Note that different root items must be used for getting data that is posted to the outgoing document and for getting data from the document that is used to update application data.</span></span>   
9. <span data-ttu-id="78bcd-125">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="78bcd-125">Click New to open the drop dialog.</span></span>
10. <span data-ttu-id="78bcd-126">Nel campo Nome digitare "Intestazione archivio".</span><span class="sxs-lookup"><span data-stu-id="78bcd-126">In the Name field, type 'Archive header'.</span></span>
    * <span data-ttu-id="78bcd-127">Intestazione archivio</span><span class="sxs-lookup"><span data-stu-id="78bcd-127">Archive header</span></span>  
11. <span data-ttu-id="78bcd-128">Nel campo Tipo di articolo selezionare "Elenco di record".</span><span class="sxs-lookup"><span data-stu-id="78bcd-128">In the Item type field, select 'Record list'.</span></span>
12. <span data-ttu-id="78bcd-129">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="78bcd-129">Click Add.</span></span>
    * <span data-ttu-id="78bcd-130">Poiché verrà creato un record per ogni report Intrastat generato, è necessario creare un nuovo articolo per il record.</span><span class="sxs-lookup"><span data-stu-id="78bcd-130">Because you will create a record for each Intrastat report that is generated, you must create a new item for that.</span></span>  
13. <span data-ttu-id="78bcd-131">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="78bcd-131">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="78bcd-132">Nel campo Nome digitare 'Nome file'.</span><span class="sxs-lookup"><span data-stu-id="78bcd-132">In the Name field, type 'File name'.</span></span>
    * <span data-ttu-id="78bcd-133">Nome file</span><span class="sxs-lookup"><span data-stu-id="78bcd-133">File name</span></span>  
15. <span data-ttu-id="78bcd-134">Nel campo Tipo di articolo selezionare "Stringa".</span><span class="sxs-lookup"><span data-stu-id="78bcd-134">In the Item type field, select 'String'.</span></span>
16. <span data-ttu-id="78bcd-135">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="78bcd-135">Click Add.</span></span>
17. <span data-ttu-id="78bcd-136">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="78bcd-136">Click New to open the drop dialog.</span></span>
18. <span data-ttu-id="78bcd-137">Nel campo Nome digitare "Numero di righe".</span><span class="sxs-lookup"><span data-stu-id="78bcd-137">In the Name field, type 'Number of lines'.</span></span>
    * <span data-ttu-id="78bcd-138">Numero di righe</span><span class="sxs-lookup"><span data-stu-id="78bcd-138">Number of lines</span></span>  
19. <span data-ttu-id="78bcd-139">Nel campo Tipo di articolo selezionare "Intero".</span><span class="sxs-lookup"><span data-stu-id="78bcd-139">In the Item type field, select 'Integer'.</span></span>
20. <span data-ttu-id="78bcd-140">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="78bcd-140">Click Add.</span></span>
    * <span data-ttu-id="78bcd-141">Aggiungere tale articolo per rappresentare il numero di transazioni Intrastat dichiarate durante il processo di dichiarazione corrente.</span><span class="sxs-lookup"><span data-stu-id="78bcd-141">Add this item to represent the number of Intrastat transactions that are reported during the current reporting process.</span></span>  
21. <span data-ttu-id="78bcd-142">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="78bcd-142">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="78bcd-143">Nel campo Nome digitare "Righe archivio".</span><span class="sxs-lookup"><span data-stu-id="78bcd-143">In the Name field, type 'Archive lines'.</span></span>
    * <span data-ttu-id="78bcd-144">Righe archivio</span><span class="sxs-lookup"><span data-stu-id="78bcd-144">Archive lines</span></span>  
23. <span data-ttu-id="78bcd-145">Nel campo Tipo di articolo selezionare "Elenco di record".</span><span class="sxs-lookup"><span data-stu-id="78bcd-145">In the Item type field, select 'Record list'.</span></span>
24. <span data-ttu-id="78bcd-146">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="78bcd-146">Click Add.</span></span>
    * <span data-ttu-id="78bcd-147">Aggiungere tale articolo per rappresentare l'elenco di transazioni Intrastat dichiarate durante il processo di dichiarazione corrente.</span><span class="sxs-lookup"><span data-stu-id="78bcd-147">Add this item to represent the list of Intrastat transactions that are reported during the current reporting process.</span></span>  
25. <span data-ttu-id="78bcd-148">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="78bcd-148">Click New to open the drop dialog.</span></span>
26. <span data-ttu-id="78bcd-149">Nel campo Nome digitare "Importo".</span><span class="sxs-lookup"><span data-stu-id="78bcd-149">In the Name field, type 'Amount'.</span></span>
    * <span data-ttu-id="78bcd-150">Importo</span><span class="sxs-lookup"><span data-stu-id="78bcd-150">Amount</span></span>  
27. <span data-ttu-id="78bcd-151">Nel campo Tipo di articolo selezionare "Reale".</span><span class="sxs-lookup"><span data-stu-id="78bcd-151">In the Item type field, select 'Real'.</span></span>
28. <span data-ttu-id="78bcd-152">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="78bcd-152">Click Add.</span></span>
29. <span data-ttu-id="78bcd-153">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="78bcd-153">Click New to open the drop dialog.</span></span>
30. <span data-ttu-id="78bcd-154">Nel campo Nome digitare "ID record voce doganale".</span><span class="sxs-lookup"><span data-stu-id="78bcd-154">In the Name field, type 'Commodity rec id'.</span></span>
    * <span data-ttu-id="78bcd-155">ID record voce doganale</span><span class="sxs-lookup"><span data-stu-id="78bcd-155">Commodity rec id</span></span>  
31. <span data-ttu-id="78bcd-156">Nel campo Tipo di articolo selezionare "Int64".</span><span class="sxs-lookup"><span data-stu-id="78bcd-156">In the Item type field, select 'Int64'.</span></span>
32. <span data-ttu-id="78bcd-157">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="78bcd-157">Click Add.</span></span>
33. <span data-ttu-id="78bcd-158">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="78bcd-158">Click New to open the drop dialog.</span></span>
34. <span data-ttu-id="78bcd-159">Nel campo Nome digitare "Numero articolo".</span><span class="sxs-lookup"><span data-stu-id="78bcd-159">In the Name field, type 'Item number'.</span></span>
    * <span data-ttu-id="78bcd-160">Numero articolo</span><span class="sxs-lookup"><span data-stu-id="78bcd-160">Item number</span></span>  
35. <span data-ttu-id="78bcd-161">Nel campo Tipo di articolo selezionare "Stringa".</span><span class="sxs-lookup"><span data-stu-id="78bcd-161">In the Item type field, select 'String'.</span></span>
36. <span data-ttu-id="78bcd-162">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="78bcd-162">Click Add.</span></span>
37. <span data-ttu-id="78bcd-163">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="78bcd-163">Click Save.</span></span>
38. <span data-ttu-id="78bcd-164">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="78bcd-164">Close the page.</span></span>

## <a name="modify-model-mapping"></a><span data-ttu-id="78bcd-165">Modificare il mapping di modello</span><span class="sxs-lookup"><span data-stu-id="78bcd-165">Modify model mapping</span></span>
1. <span data-ttu-id="78bcd-166">Nella struttura espandere "Intrastat (model)".</span><span class="sxs-lookup"><span data-stu-id="78bcd-166">In the tree, expand 'Intrastat (model)'.</span></span>
2. <span data-ttu-id="78bcd-167">Nella struttura selezionare "Intrastat (model)\Intrastat (mapping)".</span><span class="sxs-lookup"><span data-stu-id="78bcd-167">In the tree, select 'Intrastat (model)\Intrastat (mapping)'.</span></span>
    * <span data-ttu-id="78bcd-168">Modificare il mapping di modello esistente per iniziare a utilizzarlo per l'aggiornamento dei dati dell'applicazione e per archiviare i dettagli di dichiarazione Intrastat.</span><span class="sxs-lookup"><span data-stu-id="78bcd-168">Modify the existing model mapping to start using it for  the application data update and to archive Intrastat reporting details.</span></span>  
3. <span data-ttu-id="78bcd-169">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="78bcd-169">Click Designer.</span></span>
4. <span data-ttu-id="78bcd-170">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="78bcd-170">Click New.</span></span>
5. <span data-ttu-id="78bcd-171">Nel campo Nome digitare "Aggiorna archivio".</span><span class="sxs-lookup"><span data-stu-id="78bcd-171">In the Name field, type 'Update archive'.</span></span>
    * <span data-ttu-id="78bcd-172">Aggiorna archivio</span><span class="sxs-lookup"><span data-stu-id="78bcd-172">Update archive</span></span>  
6. <span data-ttu-id="78bcd-173">Nel campo Direzione selezionare "A destinazione".</span><span class="sxs-lookup"><span data-stu-id="78bcd-173">In the Direction field, select 'To destination'.</span></span>
7. <span data-ttu-id="78bcd-174">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="78bcd-174">Click Save.</span></span>
    * <span data-ttu-id="78bcd-175">Questo nuovo mapping specifica il flusso di dati per lo spostamento dei dati (dettagli dichiarazione Intrastat) dal modello dati alle tabelle dell'applicazione (destinazione dell'aggiornamento).</span><span class="sxs-lookup"><span data-stu-id="78bcd-175">This new mapping specifies the data flow for moving data (Intrastat reporting details) from the data model to the application tables (the update destination).</span></span> <span data-ttu-id="78bcd-176">Si noti che è necessario utilizzare elementi radice del modello diversi per ottenere i dati dall'applicazione per il processo di dichiarazione e quindi utilizzare i dati dal modello dati per l'aggiornamento dei dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="78bcd-176">Note that different model's root items must be used to get data from the application for the reporting process and then use the data from data model for the application data update.</span></span>   
8. <span data-ttu-id="78bcd-177">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="78bcd-177">Click Designer.</span></span>
9. <span data-ttu-id="78bcd-178">Nella struttura selezionare "Data model\Data model".</span><span class="sxs-lookup"><span data-stu-id="78bcd-178">In the tree, select 'Data model\Data model'.</span></span>
    * <span data-ttu-id="78bcd-179">Aggiungere l'origine dati necessaria.</span><span class="sxs-lookup"><span data-stu-id="78bcd-179">Add the required data source.</span></span> <span data-ttu-id="78bcd-180">Si tratta del modello dati che contiene i dettagli delle transazioni Intrastat dichiarate che devono essere archiviate.</span><span class="sxs-lookup"><span data-stu-id="78bcd-180">This is the data model that contains details of the reported Intrastat transactions that must be archived.</span></span>  
10. <span data-ttu-id="78bcd-181">Fare clic su Aggiungi radice.</span><span class="sxs-lookup"><span data-stu-id="78bcd-181">Click Add root.</span></span>
11. <span data-ttu-id="78bcd-182">Nel campo Nome digitare "modello".</span><span class="sxs-lookup"><span data-stu-id="78bcd-182">In the Name field, type 'model'.</span></span>
    * <span data-ttu-id="78bcd-183">modello</span><span class="sxs-lookup"><span data-stu-id="78bcd-183">model</span></span>  
12. <span data-ttu-id="78bcd-184">Nel campo Definizione immettere o selezionare il valore "Per l'aggiornamento dei dati dell'applicazione".</span><span class="sxs-lookup"><span data-stu-id="78bcd-184">In the Definition field, enter or select the value 'For application data update'.</span></span>
    * <span data-ttu-id="78bcd-185">Per l'aggiornamento dei dati dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="78bcd-185">For application data update</span></span>  
13. <span data-ttu-id="78bcd-186">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="78bcd-186">Click OK.</span></span>
14. <span data-ttu-id="78bcd-187">Nella struttura , espandere il "modello".</span><span class="sxs-lookup"><span data-stu-id="78bcd-187">In the tree, expand 'model'.</span></span>
15. <span data-ttu-id="78bcd-188">Nella struttura selezionare "Funzioni\Campo calcolato".</span><span class="sxs-lookup"><span data-stu-id="78bcd-188">In the tree, select 'Functions\Calculated field'.</span></span>
16. <span data-ttu-id="78bcd-189">Nella struttura selezionare "model\Archive header".</span><span class="sxs-lookup"><span data-stu-id="78bcd-189">In the tree, select 'model\Archive header'.</span></span>
17. <span data-ttu-id="78bcd-190">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="78bcd-190">Click Add.</span></span>
    * <span data-ttu-id="78bcd-191">Poiché si desidera enumerare le transazioni Intrastat dichiarate per l'archiviazione, è necessario aggiungere l'origine dati appropriata.</span><span class="sxs-lookup"><span data-stu-id="78bcd-191">Because you want to enumerate reported Intrastat transactions for archiving, the appropriate data source must be added.</span></span>  
18. <span data-ttu-id="78bcd-192">Nel campo Nome digitare "Righe enumerate".</span><span class="sxs-lookup"><span data-stu-id="78bcd-192">In the Name field, type 'Enumerated lines'.</span></span>
    * <span data-ttu-id="78bcd-193">Righe enumerate</span><span class="sxs-lookup"><span data-stu-id="78bcd-193">Enumerated lines</span></span>  
19. <span data-ttu-id="78bcd-194">Fare clic su Modifica formula.</span><span class="sxs-lookup"><span data-stu-id="78bcd-194">Click Edit formula.</span></span>
20. <span data-ttu-id="78bcd-195">Nella struttura selezionare "List\ENUMERATE".</span><span class="sxs-lookup"><span data-stu-id="78bcd-195">In the tree, select 'List\ENUMERATE'.</span></span>
21. <span data-ttu-id="78bcd-196">Fare clic su Aggiungi funzione.</span><span class="sxs-lookup"><span data-stu-id="78bcd-196">Click Add function.</span></span>
22. <span data-ttu-id="78bcd-197">Nella struttura , espandere il "modello".</span><span class="sxs-lookup"><span data-stu-id="78bcd-197">In the tree, expand 'model'.</span></span>
23. <span data-ttu-id="78bcd-198">Nella struttura espandere "model\Archive header".</span><span class="sxs-lookup"><span data-stu-id="78bcd-198">In the tree, expand 'model\Archive header'.</span></span>
24. <span data-ttu-id="78bcd-199">Nella struttura selezionare "model\Archive header\Archive lines".</span><span class="sxs-lookup"><span data-stu-id="78bcd-199">In the tree, select 'model\Archive header\Archive lines'.</span></span>
25. <span data-ttu-id="78bcd-200">Fare clic su Aggiungi origine dati.</span><span class="sxs-lookup"><span data-stu-id="78bcd-200">Click Add data source.</span></span>
26. <span data-ttu-id="78bcd-201">Nel campo Formula immettere "ENUMERATE(model.'Archive header'.'Archive lines')".</span><span class="sxs-lookup"><span data-stu-id="78bcd-201">In the Formula field, enter 'ENUMERATE(model.'Archive header'.'Archive lines')'.</span></span>
    * <span data-ttu-id="78bcd-202">ENUMERATE(model.'Archive header'.'Archive lines')</span><span class="sxs-lookup"><span data-stu-id="78bcd-202">ENUMERATE(model.'Archive header'.'Archive lines')</span></span>  
27. <span data-ttu-id="78bcd-203">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="78bcd-203">Click Save.</span></span>
28. <span data-ttu-id="78bcd-204">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="78bcd-204">Close the page.</span></span>
29. <span data-ttu-id="78bcd-205">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="78bcd-205">Click OK.</span></span>
30. <span data-ttu-id="78bcd-206">Fare clic su Aggiungi destinazione.</span><span class="sxs-lookup"><span data-stu-id="78bcd-206">Click Add destination.</span></span>
    * <span data-ttu-id="78bcd-207">Aggiungere le tabelle dell'applicazione come destinazioni necessarie che richiedono che gli aggiornamenti archivino dettagli delle transazioni Intrastat dichiarate.</span><span class="sxs-lookup"><span data-stu-id="78bcd-207">Add application tables as required destinations that require updates to archive details of reported Intrastat transactions.</span></span>  
31. <span data-ttu-id="78bcd-208">Nel campo Nome digitare "Archivio".</span><span class="sxs-lookup"><span data-stu-id="78bcd-208">In the Name field, type 'Archive'.</span></span>
    * <span data-ttu-id="78bcd-209">Archivia</span><span class="sxs-lookup"><span data-stu-id="78bcd-209">Archive</span></span>  
32. <span data-ttu-id="78bcd-210">Nel campo Nome tabella digitare "IntrastatArchiveGeneral".</span><span class="sxs-lookup"><span data-stu-id="78bcd-210">In the Table name field, type 'IntrastatArchiveGeneral'.</span></span>
    * <span data-ttu-id="78bcd-211">IntrastatArchiveGeneral</span><span class="sxs-lookup"><span data-stu-id="78bcd-211">IntrastatArchiveGeneral</span></span>  
    * <span data-ttu-id="78bcd-212">Mantenere l'azione record "Inserisci" in modo da poter aggiungere record durante l'archiviazione dei dettagli di ogni processo di dichiarazione Intrastat.</span><span class="sxs-lookup"><span data-stu-id="78bcd-212">Keep the record action 'Insert' so you can add records during the detail archiving of each Intrastat reporting process.</span></span>  
33. <span data-ttu-id="78bcd-213">Selezionare Sì nel campo Registro informazioni record.</span><span class="sxs-lookup"><span data-stu-id="78bcd-213">Select Yes in the Record infolog field.</span></span>
    * <span data-ttu-id="78bcd-214">Selezionare Sì per ottenere informazioni sui problemi relativi all'aggiornamento dei dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="78bcd-214">Select Yes to get information about issues with the application data update.</span></span>  
34. <span data-ttu-id="78bcd-215">Selezionare Sì nel campo Ignora convalida azione record.</span><span class="sxs-lookup"><span data-stu-id="78bcd-215">Select Yes in the Skip record action validation field.</span></span>
    * <span data-ttu-id="78bcd-216">Selezionare Sì per eliminare gli errori di convalida sul campo "ID archivio Intrastat" vuoto.</span><span class="sxs-lookup"><span data-stu-id="78bcd-216">Select Yes to suppress validation errors about the empty 'Intrastat archive ID' field.</span></span> <span data-ttu-id="78bcd-217">Questa operazione verrà eseguita dopo l'aggiunta dei record, in base alle impostazioni del numero progressivo configurate per la tabella nel modulo Parametri per il commercio estero.</span><span class="sxs-lookup"><span data-stu-id="78bcd-217">This will be done after records are added, based on the sequence number settings that are configured for this table in the Foreign trade parameters form.</span></span>  
35. <span data-ttu-id="78bcd-218">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="78bcd-218">Click OK.</span></span>
    * <span data-ttu-id="78bcd-219">Associare elementi dell'origine dati aggiunta (il modello filtrato in base all'elemento radice selezionato) con elementi dalla destinazione aggiunta.</span><span class="sxs-lookup"><span data-stu-id="78bcd-219">Bind elements of the added data source (the filtered model based on the selected root item) with elements from the added destination.</span></span>  
36. <span data-ttu-id="78bcd-220">Nella struttura espandere "Archive".</span><span class="sxs-lookup"><span data-stu-id="78bcd-220">In the tree, expand 'Archive'.</span></span>
37. <span data-ttu-id="78bcd-221">Nella struttura espandere "Archive\<Relations".</span><span class="sxs-lookup"><span data-stu-id="78bcd-221">In the tree, expand 'Archive\<Relations'.</span></span>
38. <span data-ttu-id="78bcd-222">Nella struttura espandere "Archive\<Relations\IntrastatArchiveDetail".</span><span class="sxs-lookup"><span data-stu-id="78bcd-222">In the tree, expand 'Archive\<Relations\IntrastatArchiveDetail'.</span></span>
39. <span data-ttu-id="78bcd-223">Nella struttura selezionare "Archive\<Relations\IntrastatArchiveDetail\Amount(AmountMST)".</span><span class="sxs-lookup"><span data-stu-id="78bcd-223">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Amount(AmountMST)'.</span></span>
40. <span data-ttu-id="78bcd-224">Nella struttura espandere "model\Archive header\Enumerated lines".</span><span class="sxs-lookup"><span data-stu-id="78bcd-224">In the tree, expand 'model\Archive header\Enumerated lines'.</span></span>
41. <span data-ttu-id="78bcd-225">Nella struttura espandere "model\Archive header\Enumerated lines\Value".</span><span class="sxs-lookup"><span data-stu-id="78bcd-225">In the tree, expand 'model\Archive header\Enumerated lines\Value'.</span></span>
42. <span data-ttu-id="78bcd-226">Nella struttura selezionare "model\Archive header\Enumerated lines\Value\Amount".</span><span class="sxs-lookup"><span data-stu-id="78bcd-226">In the tree, select 'model\Archive header\Enumerated lines\Value\Amount'.</span></span>
43. <span data-ttu-id="78bcd-227">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="78bcd-227">Click Bind.</span></span>
44. <span data-ttu-id="78bcd-228">Nella struttura selezionare "Archive\<Relations\IntrastatArchiveDetail\Commodity(IntrastatCommodity)".</span><span class="sxs-lookup"><span data-stu-id="78bcd-228">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Commodity(IntrastatCommodity)'.</span></span>
45. <span data-ttu-id="78bcd-229">Nella struttura selezionare "model\Archive header\Enumerated lines\Value\Commodity rec id".</span><span class="sxs-lookup"><span data-stu-id="78bcd-229">In the tree, select 'model\Archive header\Enumerated lines\Value\Commodity rec id'.</span></span>
46. <span data-ttu-id="78bcd-230">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="78bcd-230">Click Bind.</span></span>
47. <span data-ttu-id="78bcd-231">Nella struttura selezionare "Archive\<Relations\IntrastatArchiveDetail\Item number(ItemId)".</span><span class="sxs-lookup"><span data-stu-id="78bcd-231">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Item number(ItemId)'.</span></span>
48. <span data-ttu-id="78bcd-232">Nella struttura selezionare "model\Archive header\Enumerated lines\Value\Item number".</span><span class="sxs-lookup"><span data-stu-id="78bcd-232">In the tree, select 'model\Archive header\Enumerated lines\Value\Item number'.</span></span>
49. <span data-ttu-id="78bcd-233">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="78bcd-233">Click Bind.</span></span>
50. <span data-ttu-id="78bcd-234">Nella struttura selezionare "Archive\<Relations\IntrastatArchiveDetail\Line number(LineNumber)".</span><span class="sxs-lookup"><span data-stu-id="78bcd-234">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Line number(LineNumber)'.</span></span>
51. <span data-ttu-id="78bcd-235">Nella struttura selezionare "model\Archive header\Enumerated lines\Number".</span><span class="sxs-lookup"><span data-stu-id="78bcd-235">In the tree, select 'model\Archive header\Enumerated lines\Number'.</span></span>
52. <span data-ttu-id="78bcd-236">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="78bcd-236">Click Bind.</span></span>
53. <span data-ttu-id="78bcd-237">Nella struttura selezionare "Archive\<Relations\IntrastatArchiveDetail".</span><span class="sxs-lookup"><span data-stu-id="78bcd-237">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail'.</span></span>
54. <span data-ttu-id="78bcd-238">Nella struttura selezionare "model\Archive header\Enumerated lines".</span><span class="sxs-lookup"><span data-stu-id="78bcd-238">In the tree, select 'model\Archive header\Enumerated lines'.</span></span>
55. <span data-ttu-id="78bcd-239">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="78bcd-239">Click Bind.</span></span>
56. <span data-ttu-id="78bcd-240">Nella struttura selezionare "Archive\File name(FileName)".</span><span class="sxs-lookup"><span data-stu-id="78bcd-240">In the tree, select 'Archive\File name(FileName)'.</span></span>
57. <span data-ttu-id="78bcd-241">Nella struttura selezionare "model\Archive header\File name".</span><span class="sxs-lookup"><span data-stu-id="78bcd-241">In the tree, select 'model\Archive header\File name'.</span></span>
58. <span data-ttu-id="78bcd-242">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="78bcd-242">Click Bind.</span></span>
59. <span data-ttu-id="78bcd-243">Nella struttura selezionare "Archive\Number of lines(NumberOfLines)".</span><span class="sxs-lookup"><span data-stu-id="78bcd-243">In the tree, select 'Archive\Number of lines(NumberOfLines)'.</span></span>
60. <span data-ttu-id="78bcd-244">Nella struttura selezionare "model\Archive header\Number of lines".</span><span class="sxs-lookup"><span data-stu-id="78bcd-244">In the tree, select 'model\Archive header\Number of lines'.</span></span>
61. <span data-ttu-id="78bcd-245">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="78bcd-245">Click Bind.</span></span>
62. <span data-ttu-id="78bcd-246">Nella struttura selezionare "Archive".</span><span class="sxs-lookup"><span data-stu-id="78bcd-246">In the tree, select 'Archive'.</span></span>
63. <span data-ttu-id="78bcd-247">Nella struttura selezionare "model\Archive header".</span><span class="sxs-lookup"><span data-stu-id="78bcd-247">In the tree, select 'model\Archive header'.</span></span>
64. <span data-ttu-id="78bcd-248">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="78bcd-248">Click Bind.</span></span>
65. <span data-ttu-id="78bcd-249">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="78bcd-249">Click Save.</span></span>
66. <span data-ttu-id="78bcd-250">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="78bcd-250">Close the page.</span></span>
67. <span data-ttu-id="78bcd-251">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="78bcd-251">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]