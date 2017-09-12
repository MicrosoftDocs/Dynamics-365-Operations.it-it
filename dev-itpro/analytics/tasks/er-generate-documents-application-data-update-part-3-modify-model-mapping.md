--- 
title: Modificare il modello e il mapping per generare i documenti con l'aggiornamento dei dati dell'applicazione per la creazione di report elettronici (ER)
description: "Per completare i passaggi di questa procedura, è necessario completare la procedura \"ER Generare documenti con l'aggiornamento dei dati dell'applicazione (Parte 2: Generare documenti)\"."
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: aa173138eaf0178f2a942a88eafe80d4bac4d6a8
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="modify-model-and-mapping-to-generate-documents-with-application-data-update-for-electronic-reporting-er"></a><span data-ttu-id="54d79-103">Modificare il modello e il mapping per generare i documenti con l'aggiornamento dei dati dell'applicazione per la creazione di report elettronici (ER)</span><span class="sxs-lookup"><span data-stu-id="54d79-103">Modify model and mapping to generate documents with application data update for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="54d79-104">Per completare i passaggi di questa procedura, è necessario completare la procedura "ER Generare documenti con l'aggiornamento dei dati dell'applicazione (Parte 2: Generare documenti)".</span><span class="sxs-lookup"><span data-stu-id="54d79-104">To complete the steps in this procedure, you must first complete the procedure, “ER Generate documents with application data update (Part 2: Generate documents)”.</span></span> 

<span data-ttu-id="54d79-105">I passaggi di questa procedura descrivono come progettare le configurazioni ER per generare un documento elettronico e aggiornare i dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="54d79-105">The steps in this procedure explain how to design Electronic reporting (ER) configurations to generate an electronic document and update application data.</span></span> <span data-ttu-id="54d79-106">In questa procedura verranno modificate le configurazioni ER per iniziare a utilizzarle per generare i documenti elettronici e per aggiornare i dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="54d79-106">In this procedure, you will modify the ER configurations to start using them to generate electronic documents and update application data.</span></span> <span data-ttu-id="54d79-107">Questa procedura viene creata per utenti con il ruolo di amministratore di sistema o di sviluppatore di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="54d79-107">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="54d79-108">Tali passaggi possono essere completati mediante il set di dati DEMF.</span><span class="sxs-lookup"><span data-stu-id="54d79-108">These steps can be completed using the DEMF dataset.</span></span>


## <a name="modify-data-model"></a><span data-ttu-id="54d79-109">Modificare il modello dati</span><span class="sxs-lookup"><span data-stu-id="54d79-109">Modify data model</span></span>
1. <span data-ttu-id="54d79-110">Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.</span><span class="sxs-lookup"><span data-stu-id="54d79-110">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="54d79-111">Nella struttura selezionare "Intrastat (model)".</span><span class="sxs-lookup"><span data-stu-id="54d79-111">In the tree, select 'Intrastat (model)'.</span></span>
    * <span data-ttu-id="54d79-112">A questo punto verranno estese le modalità di utilizzo del modello dati.</span><span class="sxs-lookup"><span data-stu-id="54d79-112">You will extend how you use the data model.</span></span> <span data-ttu-id="54d79-113">Oltre a utilizzarlo come origine dati per generare il report Intrastat, il modello dati verrà utilizzato per raccogliere informazioni dettagliate sul processo di dichiarazione Intrastat.</span><span class="sxs-lookup"><span data-stu-id="54d79-113">Besides using it as data source to generate the Intrastat report, the data model will be used to collect details about the Intrastat reporting process.</span></span> <span data-ttu-id="54d79-114">I dettagli verranno utilizzati per aggiornare i dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="54d79-114">The details will then be used to update application data.</span></span>   
3. <span data-ttu-id="54d79-115">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="54d79-115">Click Designer.</span></span>
4. <span data-ttu-id="54d79-116">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="54d79-116">Click New to open the drop dialog.</span></span>
5. <span data-ttu-id="54d79-117">Nel campo Nuovo nodo come immettere 'Radice modello'.</span><span class="sxs-lookup"><span data-stu-id="54d79-117">In the New node as a field, enter 'Model root'.</span></span>
6. <span data-ttu-id="54d79-118">Nel campo Nome digitare "Per l'aggiornamento dei dati dell'applicazione".</span><span class="sxs-lookup"><span data-stu-id="54d79-118">In the Name field, type 'For application data update'.</span></span>
    * <span data-ttu-id="54d79-119">Per l'aggiornamento dei dati dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="54d79-119">For application data update</span></span>  
7. <span data-ttu-id="54d79-120">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="54d79-120">Click Add.</span></span>
8. <span data-ttu-id="54d79-121">Nella struttura selezionare "For application data update".</span><span class="sxs-lookup"><span data-stu-id="54d79-121">In the tree, select 'For application data update'.</span></span>
    * <span data-ttu-id="54d79-122">Il nuovo elemento radice viene aggiunto per specificare il flusso di dati per lo spostamento dei dati dal report Intrastat (utilizzato come origine dati) alle tabelle dell'applicazione (destinazione dell'aggiornamento).</span><span class="sxs-lookup"><span data-stu-id="54d79-122">This new root item is added to specify the data flow for moving data from the Intrastat report (used as a data source) to the application tables (the update destination).</span></span> <span data-ttu-id="54d79-123">Si noti che è necessario utilizzare elementi radice diversi per ottenere i dati registrati nel documento in uscita e per ottenere i dati del documento utilizzato per aggiornare i dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="54d79-123">Note that different root items must be used for getting data that is posted to the outgoing document and for getting data from the document that is used to update application data.</span></span>   
9. <span data-ttu-id="54d79-124">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="54d79-124">Click New to open the drop dialog.</span></span>
10. <span data-ttu-id="54d79-125">Nel campo Nome digitare "Intestazione archivio".</span><span class="sxs-lookup"><span data-stu-id="54d79-125">In the Name field, type 'Archive header'.</span></span>
    * <span data-ttu-id="54d79-126">Intestazione archivio</span><span class="sxs-lookup"><span data-stu-id="54d79-126">Archive header</span></span>  
11. <span data-ttu-id="54d79-127">Nel campo Tipo di articolo selezionare "Elenco di record".</span><span class="sxs-lookup"><span data-stu-id="54d79-127">In the Item type field, select 'Record list'.</span></span>
12. <span data-ttu-id="54d79-128">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="54d79-128">Click Add.</span></span>
    * <span data-ttu-id="54d79-129">Poiché verrà creato un record per ogni report Intrastat generato, è necessario creare un nuovo articolo per il record.</span><span class="sxs-lookup"><span data-stu-id="54d79-129">Because you will create a record for each Intrastat report that is generated, you must create a new item for that.</span></span>  
13. <span data-ttu-id="54d79-130">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="54d79-130">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="54d79-131">Nel campo Nome digitare 'Nome file'.</span><span class="sxs-lookup"><span data-stu-id="54d79-131">In the Name field, type 'File name'.</span></span>
    * <span data-ttu-id="54d79-132">Nome file</span><span class="sxs-lookup"><span data-stu-id="54d79-132">File name</span></span>  
15. <span data-ttu-id="54d79-133">Nel campo Tipo di articolo selezionare "Stringa".</span><span class="sxs-lookup"><span data-stu-id="54d79-133">In the Item type field, select 'String'.</span></span>
16. <span data-ttu-id="54d79-134">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="54d79-134">Click Add.</span></span>
17. <span data-ttu-id="54d79-135">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="54d79-135">Click New to open the drop dialog.</span></span>
18. <span data-ttu-id="54d79-136">Nel campo Nome digitare "Numero di righe".</span><span class="sxs-lookup"><span data-stu-id="54d79-136">In the Name field, type 'Number of lines'.</span></span>
    * <span data-ttu-id="54d79-137">Numero di righe</span><span class="sxs-lookup"><span data-stu-id="54d79-137">Number of lines</span></span>  
19. <span data-ttu-id="54d79-138">Nel campo Tipo di articolo selezionare "Intero".</span><span class="sxs-lookup"><span data-stu-id="54d79-138">In the Item type field, select 'Integer'.</span></span>
20. <span data-ttu-id="54d79-139">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="54d79-139">Click Add.</span></span>
    * <span data-ttu-id="54d79-140">Aggiungere tale articolo per rappresentare il numero di transazioni Intrastat dichiarate durante il processo di dichiarazione corrente.</span><span class="sxs-lookup"><span data-stu-id="54d79-140">Add this item to represent the number of Intrastat transactions that are reported during the current reporting process.</span></span>  
21. <span data-ttu-id="54d79-141">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="54d79-141">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="54d79-142">Nel campo Nome digitare "Righe archivio".</span><span class="sxs-lookup"><span data-stu-id="54d79-142">In the Name field, type 'Archive lines'.</span></span>
    * <span data-ttu-id="54d79-143">Righe archivio</span><span class="sxs-lookup"><span data-stu-id="54d79-143">Archive lines</span></span>  
23. <span data-ttu-id="54d79-144">Nel campo Tipo di articolo selezionare "Elenco di record".</span><span class="sxs-lookup"><span data-stu-id="54d79-144">In the Item type field, select 'Record list'.</span></span>
24. <span data-ttu-id="54d79-145">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="54d79-145">Click Add.</span></span>
    * <span data-ttu-id="54d79-146">Aggiungere tale articolo per rappresentare l'elenco di transazioni Intrastat dichiarate durante il processo di dichiarazione corrente.</span><span class="sxs-lookup"><span data-stu-id="54d79-146">Add this item to represent the list of Intrastat transactions that are reported during the current reporting process.</span></span>  
25. <span data-ttu-id="54d79-147">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="54d79-147">Click New to open the drop dialog.</span></span>
26. <span data-ttu-id="54d79-148">Nel campo Nome digitare "Importo".</span><span class="sxs-lookup"><span data-stu-id="54d79-148">In the Name field, type 'Amount'.</span></span>
    * <span data-ttu-id="54d79-149">Importo</span><span class="sxs-lookup"><span data-stu-id="54d79-149">Amount</span></span>  
27. <span data-ttu-id="54d79-150">Nel campo Tipo di articolo selezionare "Reale".</span><span class="sxs-lookup"><span data-stu-id="54d79-150">In the Item type field, select 'Real'.</span></span>
28. <span data-ttu-id="54d79-151">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="54d79-151">Click Add.</span></span>
29. <span data-ttu-id="54d79-152">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="54d79-152">Click New to open the drop dialog.</span></span>
30. <span data-ttu-id="54d79-153">Nel campo Nome digitare "ID record voce doganale".</span><span class="sxs-lookup"><span data-stu-id="54d79-153">In the Name field, type 'Commodity rec id'.</span></span>
    * <span data-ttu-id="54d79-154">ID record voce doganale</span><span class="sxs-lookup"><span data-stu-id="54d79-154">Commodity rec id</span></span>  
31. <span data-ttu-id="54d79-155">Nel campo Tipo di articolo selezionare "Int64".</span><span class="sxs-lookup"><span data-stu-id="54d79-155">In the Item type field, select 'Int64'.</span></span>
32. <span data-ttu-id="54d79-156">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="54d79-156">Click Add.</span></span>
33. <span data-ttu-id="54d79-157">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="54d79-157">Click New to open the drop dialog.</span></span>
34. <span data-ttu-id="54d79-158">Nel campo Nome digitare "Numero articolo".</span><span class="sxs-lookup"><span data-stu-id="54d79-158">In the Name field, type 'Item number'.</span></span>
    * <span data-ttu-id="54d79-159">Numero articolo</span><span class="sxs-lookup"><span data-stu-id="54d79-159">Item number</span></span>  
35. <span data-ttu-id="54d79-160">Nel campo Tipo di articolo selezionare "Stringa".</span><span class="sxs-lookup"><span data-stu-id="54d79-160">In the Item type field, select 'String'.</span></span>
36. <span data-ttu-id="54d79-161">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="54d79-161">Click Add.</span></span>
37. <span data-ttu-id="54d79-162">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="54d79-162">Click Save.</span></span>
38. <span data-ttu-id="54d79-163">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="54d79-163">Close the page.</span></span>

## <a name="modify-model-mapping"></a><span data-ttu-id="54d79-164">Modificare il mapping di modello</span><span class="sxs-lookup"><span data-stu-id="54d79-164">Modify model mapping</span></span>
1. <span data-ttu-id="54d79-165">Nella struttura espandere "Intrastat (model)".</span><span class="sxs-lookup"><span data-stu-id="54d79-165">In the tree, expand 'Intrastat (model)'.</span></span>
2. <span data-ttu-id="54d79-166">Nella struttura selezionare "Intrastat (model)\Intrastat (mapping)".</span><span class="sxs-lookup"><span data-stu-id="54d79-166">In the tree, select 'Intrastat (model)\Intrastat (mapping)'.</span></span>
    * <span data-ttu-id="54d79-167">Modificare il mapping di modello esistente per iniziare a utilizzarlo per l'aggiornamento dei dati dell'applicazione e per archiviare i dettagli di dichiarazione Intrastat.</span><span class="sxs-lookup"><span data-stu-id="54d79-167">Modify the existing model mapping to start using it for  the application data update and to archive Intrastat reporting details.</span></span>  
3. <span data-ttu-id="54d79-168">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="54d79-168">Click Designer.</span></span>
4. <span data-ttu-id="54d79-169">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="54d79-169">Click New.</span></span>
5. <span data-ttu-id="54d79-170">Nel campo Nome digitare "Aggiorna archivio".</span><span class="sxs-lookup"><span data-stu-id="54d79-170">In the Name field, type 'Update archive'.</span></span>
    * <span data-ttu-id="54d79-171">Aggiorna archivio</span><span class="sxs-lookup"><span data-stu-id="54d79-171">Update archive</span></span>  
6. <span data-ttu-id="54d79-172">Nel campo Direzione selezionare "A destinazione".</span><span class="sxs-lookup"><span data-stu-id="54d79-172">In the Direction field, select 'To destination'.</span></span>
7. <span data-ttu-id="54d79-173">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="54d79-173">Click Save.</span></span>
    * <span data-ttu-id="54d79-174">Questo nuovo mapping specifica il flusso di dati per lo spostamento dei dati (dettagli dichiarazione Intrastat) dal modello dati alle tabelle dell'applicazione (destinazione dell'aggiornamento).</span><span class="sxs-lookup"><span data-stu-id="54d79-174">This new mapping specifies the data flow for moving data (Intrastat reporting details) from the data model to the application tables (the update destination).</span></span> <span data-ttu-id="54d79-175">Si noti che è necessario utilizzare elementi radice del modello diversi per ottenere i dati dall'applicazione per il processo di dichiarazione e quindi utilizzare i dati dal modello dati per l'aggiornamento dei dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="54d79-175">Note that different model’s root items must be used to get data from the application for the reporting process and then use the data from data model for the application data update.</span></span>   
8. <span data-ttu-id="54d79-176">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="54d79-176">Click Designer.</span></span>
9. <span data-ttu-id="54d79-177">Nella struttura selezionare "Data model\Data model".</span><span class="sxs-lookup"><span data-stu-id="54d79-177">In the tree, select 'Data model\Data model'.</span></span>
    * <span data-ttu-id="54d79-178">Aggiungere l'origine dati necessaria.</span><span class="sxs-lookup"><span data-stu-id="54d79-178">Add the required data source.</span></span> <span data-ttu-id="54d79-179">Si tratta del modello dati che contiene i dettagli delle transazioni Intrastat dichiarate che devono essere archiviate.</span><span class="sxs-lookup"><span data-stu-id="54d79-179">This is the data model that contains details of the reported Intrastat transactions that must be archived.</span></span>  
10. <span data-ttu-id="54d79-180">Fare clic su Aggiungi radice.</span><span class="sxs-lookup"><span data-stu-id="54d79-180">Click Add root.</span></span>
11. <span data-ttu-id="54d79-181">Nel campo Nome digitare "modello".</span><span class="sxs-lookup"><span data-stu-id="54d79-181">In the Name field, type 'model'.</span></span>
    * <span data-ttu-id="54d79-182">modello</span><span class="sxs-lookup"><span data-stu-id="54d79-182">model</span></span>  
12. <span data-ttu-id="54d79-183">Nel campo Definizione immettere o selezionare il valore "Per l'aggiornamento dei dati dell'applicazione".</span><span class="sxs-lookup"><span data-stu-id="54d79-183">In the Definition field, enter or select the value ‘For application data update’.</span></span>
    * <span data-ttu-id="54d79-184">Per l'aggiornamento dei dati dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="54d79-184">For application data update</span></span>  
13. <span data-ttu-id="54d79-185">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="54d79-185">Click OK.</span></span>
14. <span data-ttu-id="54d79-186">Nella struttura , espandere il "modello".</span><span class="sxs-lookup"><span data-stu-id="54d79-186">In the tree, expand 'model'.</span></span>
15. <span data-ttu-id="54d79-187">Nella struttura selezionare "Funzioni\Campo calcolato".</span><span class="sxs-lookup"><span data-stu-id="54d79-187">In the tree, select 'Functions\Calculated field'.</span></span>
16. <span data-ttu-id="54d79-188">Nella struttura selezionare "model\Archive header".</span><span class="sxs-lookup"><span data-stu-id="54d79-188">In the tree, select 'model\Archive header'.</span></span>
17. <span data-ttu-id="54d79-189">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="54d79-189">Click Add.</span></span>
    * <span data-ttu-id="54d79-190">Poiché si desidera enumerare le transazioni Intrastat dichiarate per l'archiviazione, è necessario aggiungere l'origine dati appropriata.</span><span class="sxs-lookup"><span data-stu-id="54d79-190">Because you want to enumerate reported Intrastat transactions for archiving, the appropriate data source must be added.</span></span>  
18. <span data-ttu-id="54d79-191">Nel campo Nome digitare "Righe enumerate".</span><span class="sxs-lookup"><span data-stu-id="54d79-191">In the Name field, type 'Enumerated lines'.</span></span>
    * <span data-ttu-id="54d79-192">Righe enumerate</span><span class="sxs-lookup"><span data-stu-id="54d79-192">Enumerated lines</span></span>  
19. <span data-ttu-id="54d79-193">Fare clic su Modifica formula.</span><span class="sxs-lookup"><span data-stu-id="54d79-193">Click Edit formula.</span></span>
20. <span data-ttu-id="54d79-194">Nella struttura selezionare "List\ENUMERATE".</span><span class="sxs-lookup"><span data-stu-id="54d79-194">In the tree, select 'List\ENUMERATE'.</span></span>
21. <span data-ttu-id="54d79-195">Fare clic su Aggiungi funzione.</span><span class="sxs-lookup"><span data-stu-id="54d79-195">Click Add function.</span></span>
22. <span data-ttu-id="54d79-196">Nella struttura , espandere il "modello".</span><span class="sxs-lookup"><span data-stu-id="54d79-196">In the tree, expand 'model'.</span></span>
23. <span data-ttu-id="54d79-197">Nella struttura espandere "model\Archive header".</span><span class="sxs-lookup"><span data-stu-id="54d79-197">In the tree, expand 'model\Archive header'.</span></span>
24. <span data-ttu-id="54d79-198">Nella struttura selezionare "model\Archive header\Archive lines".</span><span class="sxs-lookup"><span data-stu-id="54d79-198">In the tree, select 'model\Archive header\Archive lines'.</span></span>
25. <span data-ttu-id="54d79-199">Fare clic su Aggiungi origine dati.</span><span class="sxs-lookup"><span data-stu-id="54d79-199">Click Add data source.</span></span>
26. <span data-ttu-id="54d79-200">Nel campo Formula immettere "ENUMERATE(model.'Archive header'.'Archive lines')".</span><span class="sxs-lookup"><span data-stu-id="54d79-200">In the Formula field, enter 'ENUMERATE(model.'Archive header'.'Archive lines')'.</span></span>
    * <span data-ttu-id="54d79-201">ENUMERATE(model.'Archive header'.'Archive lines')</span><span class="sxs-lookup"><span data-stu-id="54d79-201">ENUMERATE(model.'Archive header'.'Archive lines')</span></span>  
27. <span data-ttu-id="54d79-202">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="54d79-202">Click Save.</span></span>
28. <span data-ttu-id="54d79-203">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="54d79-203">Close the page.</span></span>
29. <span data-ttu-id="54d79-204">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="54d79-204">Click OK.</span></span>
30. <span data-ttu-id="54d79-205">Fare clic su Aggiungi destinazione.</span><span class="sxs-lookup"><span data-stu-id="54d79-205">Click Add destination.</span></span>
    * <span data-ttu-id="54d79-206">Aggiungere le tabelle dell'applicazione come destinazioni necessarie che richiedono che gli aggiornamenti archivino dettagli delle transazioni Intrastat dichiarate.</span><span class="sxs-lookup"><span data-stu-id="54d79-206">Add application tables as required destinations that require updates to archive details of reported Intrastat transactions.</span></span>  
31. <span data-ttu-id="54d79-207">Nel campo Nome digitare "Archivio".</span><span class="sxs-lookup"><span data-stu-id="54d79-207">In the Name field, type 'Archive'.</span></span>
    * <span data-ttu-id="54d79-208">Archivia</span><span class="sxs-lookup"><span data-stu-id="54d79-208">Archive</span></span>  
32. <span data-ttu-id="54d79-209">Nel campo Nome tabella digitare "IntrastatArchiveGeneral".</span><span class="sxs-lookup"><span data-stu-id="54d79-209">In the Table name field, type 'IntrastatArchiveGeneral'.</span></span>
    * <span data-ttu-id="54d79-210">IntrastatArchiveGeneral</span><span class="sxs-lookup"><span data-stu-id="54d79-210">IntrastatArchiveGeneral</span></span>  
    * <span data-ttu-id="54d79-211">Mantenere l'azione record "Inserisci" in modo da poter aggiungere record durante l'archiviazione dei dettagli di ogni processo di dichiarazione Intrastat.</span><span class="sxs-lookup"><span data-stu-id="54d79-211">Keep the record action ‘Insert’ so you can add records during the detail archiving of each Intrastat reporting process.</span></span>  
33. <span data-ttu-id="54d79-212">Selezionare Sì nel campo Registro informazioni record.</span><span class="sxs-lookup"><span data-stu-id="54d79-212">Select Yes in the Record infolog field.</span></span>
    * <span data-ttu-id="54d79-213">Selezionare Sì per ottenere informazioni sui problemi relativi all'aggiornamento dei dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="54d79-213">Select Yes to get information about issues with the application data update.</span></span>  
34. <span data-ttu-id="54d79-214">Selezionare Sì nel campo Ignora convalida azione record.</span><span class="sxs-lookup"><span data-stu-id="54d79-214">Select Yes in the Skip record action validation field.</span></span>
    * <span data-ttu-id="54d79-215">Selezionare Sì per eliminare gli errori di convalida sul campo "ID archivio Intrastat" vuoto.</span><span class="sxs-lookup"><span data-stu-id="54d79-215">Select Yes to suppress validation errors about the empty ‘Intrastat archive ID’ field.</span></span> <span data-ttu-id="54d79-216">Questa operazione verrà eseguita dopo l'aggiunta dei record, in base alle impostazioni del numero progressivo configurate per la tabella nel modulo Parametri per il commercio estero.</span><span class="sxs-lookup"><span data-stu-id="54d79-216">This will be done after records are added, based on the sequence number settings that are configured for this table in the Foreign trade parameters form.</span></span>  
35. <span data-ttu-id="54d79-217">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="54d79-217">Click OK.</span></span>
    * <span data-ttu-id="54d79-218">Associare elementi dell'origine dati aggiunta (il modello filtrato in base all'elemento radice selezionato) con elementi dalla destinazione aggiunta.</span><span class="sxs-lookup"><span data-stu-id="54d79-218">Bind elements of the added data source (the filtered model based on the selected root item) with elements from the added destination.</span></span>  
36. <span data-ttu-id="54d79-219">Nella struttura espandere "Archive".</span><span class="sxs-lookup"><span data-stu-id="54d79-219">In the tree, expand 'Archive'.</span></span>
37. <span data-ttu-id="54d79-220">Nella struttura espandere "Archive\<Relations".</span><span class="sxs-lookup"><span data-stu-id="54d79-220">In the tree, expand 'Archive\<Relations'.</span></span>
38. <span data-ttu-id="54d79-221">Nella struttura espandere "Archive\<Relations\IntrastatArchiveDetail".</span><span class="sxs-lookup"><span data-stu-id="54d79-221">In the tree, expand 'Archive\<Relations\IntrastatArchiveDetail'.</span></span>
39. <span data-ttu-id="54d79-222">Nella struttura selezionare "Archive\<Relations\IntrastatArchiveDetail\Amount(AmountMST)".</span><span class="sxs-lookup"><span data-stu-id="54d79-222">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Amount(AmountMST)'.</span></span>
40. <span data-ttu-id="54d79-223">Nella struttura espandere "model\Archive header\Enumerated lines".</span><span class="sxs-lookup"><span data-stu-id="54d79-223">In the tree, expand 'model\Archive header\Enumerated lines'.</span></span>
41. <span data-ttu-id="54d79-224">Nella struttura espandere "model\Archive header\Enumerated lines\Value".</span><span class="sxs-lookup"><span data-stu-id="54d79-224">In the tree, expand 'model\Archive header\Enumerated lines\Value'.</span></span>
42. <span data-ttu-id="54d79-225">Nella struttura selezionare "model\Archive header\Enumerated lines\Value\Amount".</span><span class="sxs-lookup"><span data-stu-id="54d79-225">In the tree, select 'model\Archive header\Enumerated lines\Value\Amount'.</span></span>
43. <span data-ttu-id="54d79-226">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="54d79-226">Click Bind.</span></span>
44. <span data-ttu-id="54d79-227">Nella struttura selezionare "Archive\<Relations\IntrastatArchiveDetail\Commodity(IntrastatCommodity)".</span><span class="sxs-lookup"><span data-stu-id="54d79-227">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Commodity(IntrastatCommodity)'.</span></span>
45. <span data-ttu-id="54d79-228">Nella struttura selezionare "model\Archive header\Enumerated lines\Value\Commodity rec id".</span><span class="sxs-lookup"><span data-stu-id="54d79-228">In the tree, select 'model\Archive header\Enumerated lines\Value\Commodity rec id'.</span></span>
46. <span data-ttu-id="54d79-229">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="54d79-229">Click Bind.</span></span>
47. <span data-ttu-id="54d79-230">Nella struttura selezionare "Archive\<Relations\IntrastatArchiveDetail\Item number(ItemId)".</span><span class="sxs-lookup"><span data-stu-id="54d79-230">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Item number(ItemId)'.</span></span>
48. <span data-ttu-id="54d79-231">Nella struttura selezionare "model\Archive header\Enumerated lines\Value\Item number".</span><span class="sxs-lookup"><span data-stu-id="54d79-231">In the tree, select 'model\Archive header\Enumerated lines\Value\Item number'.</span></span>
49. <span data-ttu-id="54d79-232">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="54d79-232">Click Bind.</span></span>
50. <span data-ttu-id="54d79-233">Nella struttura selezionare "Archive\<Relations\IntrastatArchiveDetail\Line number(LineNumber)".</span><span class="sxs-lookup"><span data-stu-id="54d79-233">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Line number(LineNumber)'.</span></span>
51. <span data-ttu-id="54d79-234">Nella struttura selezionare "model\Archive header\Enumerated lines\Number".</span><span class="sxs-lookup"><span data-stu-id="54d79-234">In the tree, select 'model\Archive header\Enumerated lines\Number'.</span></span>
52. <span data-ttu-id="54d79-235">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="54d79-235">Click Bind.</span></span>
53. <span data-ttu-id="54d79-236">Nella struttura selezionare "Archive\<Relations\IntrastatArchiveDetail".</span><span class="sxs-lookup"><span data-stu-id="54d79-236">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail'.</span></span>
54. <span data-ttu-id="54d79-237">Nella struttura selezionare "model\Archive header\Enumerated lines".</span><span class="sxs-lookup"><span data-stu-id="54d79-237">In the tree, select 'model\Archive header\Enumerated lines'.</span></span>
55. <span data-ttu-id="54d79-238">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="54d79-238">Click Bind.</span></span>
56. <span data-ttu-id="54d79-239">Nella struttura selezionare "Archive\File name(FileName)".</span><span class="sxs-lookup"><span data-stu-id="54d79-239">In the tree, select 'Archive\File name(FileName)'.</span></span>
57. <span data-ttu-id="54d79-240">Nella struttura selezionare "model\Archive header\File name".</span><span class="sxs-lookup"><span data-stu-id="54d79-240">In the tree, select 'model\Archive header\File name'.</span></span>
58. <span data-ttu-id="54d79-241">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="54d79-241">Click Bind.</span></span>
59. <span data-ttu-id="54d79-242">Nella struttura selezionare "Archive\Number of lines(NumberOfLines)".</span><span class="sxs-lookup"><span data-stu-id="54d79-242">In the tree, select 'Archive\Number of lines(NumberOfLines)'.</span></span>
60. <span data-ttu-id="54d79-243">Nella struttura selezionare "model\Archive header\Number of lines".</span><span class="sxs-lookup"><span data-stu-id="54d79-243">In the tree, select 'model\Archive header\Number of lines'.</span></span>
61. <span data-ttu-id="54d79-244">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="54d79-244">Click Bind.</span></span>
62. <span data-ttu-id="54d79-245">Nella struttura selezionare "Archive".</span><span class="sxs-lookup"><span data-stu-id="54d79-245">In the tree, select 'Archive'.</span></span>
63. <span data-ttu-id="54d79-246">Nella struttura selezionare "model\Archive header".</span><span class="sxs-lookup"><span data-stu-id="54d79-246">In the tree, select 'model\Archive header'.</span></span>
64. <span data-ttu-id="54d79-247">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="54d79-247">Click Bind.</span></span>
65. <span data-ttu-id="54d79-248">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="54d79-248">Click Save.</span></span>
66. <span data-ttu-id="54d79-249">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="54d79-249">Close the page.</span></span>
67. <span data-ttu-id="54d79-250">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="54d79-250">Close the page.</span></span>

