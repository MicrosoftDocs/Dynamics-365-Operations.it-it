--- 
title: Creare il formato per utilizzare i file per la gestione dei documenti negli output di formato
description: "I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che utilizzi i file (allegati) di gestione documenti nell'output della creazione di report elettronici."
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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 6d5df842dbbf89f5df72c63919fc0bcbf811a09c
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---
# <a name="create-format-to-use-document-management-files-in-format-outputs"></a><span data-ttu-id="cd195-103">Creare il formato per utilizzare i file per la gestione dei documenti negli output di formato</span><span class="sxs-lookup"><span data-stu-id="cd195-103">Create format to use Document Management files in format outputs</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cd195-104">I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che utilizzi i file (allegati) di gestione documenti nell'output della creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="cd195-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="cd195-105">Questi passaggi possono essere eseguiti in qualsiasi società.</span><span class="sxs-lookup"><span data-stu-id="cd195-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="cd195-106">Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi della procedura 'ER Usare i file di gestione documenti negli output di formato (parte 2: estendere il modello dati)'.</span><span class="sxs-lookup"><span data-stu-id="cd195-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 2: Extend data model” procedure.</span></span>

<span data-ttu-id="cd195-107">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="cd195-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-format-to-process-invoices"></a><span data-ttu-id="cd195-108">Creare un formato per l'elaborazione delle fatture</span><span class="sxs-lookup"><span data-stu-id="cd195-108">Create a format to process invoices</span></span>
1. <span data-ttu-id="cd195-109">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="cd195-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="cd195-110">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="cd195-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="cd195-111">Nella struttura espandere 'Modello fattura cliente'.</span><span class="sxs-lookup"><span data-stu-id="cd195-111">In the tree, expand 'Customer invoice model'.</span></span>
4. <span data-ttu-id="cd195-112">Nella struttura selezionare 'Modello fattura cliente\Modello fattura cliente (personalizzato)'.</span><span class="sxs-lookup"><span data-stu-id="cd195-112">In the tree, select 'Customer invoice model\Customer invoice model (custom)'.</span></span>
    * <span data-ttu-id="cd195-113">Creerete un formato per generare i messaggi elettronici con informazioni su tutti i file che sono stati allegati a un ordine cliente correlato a una fattura elaborata elettronicamente.</span><span class="sxs-lookup"><span data-stu-id="cd195-113">You will create a format to generate electronic messages with information about any files that have been attached to a sales order that is related to an electronically processing invoice.</span></span>  
5. <span data-ttu-id="cd195-114">Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .</span><span class="sxs-lookup"><span data-stu-id="cd195-114">Click Create configuration to open the drop dialog.</span></span>
6. <span data-ttu-id="cd195-115">Nel campo Nuovo immettere 'Formato basato sul modello dati Modello fattura cliente (personalizzato)'.</span><span class="sxs-lookup"><span data-stu-id="cd195-115">In the New field, enter 'Format based on data model Customer invoice model (custom)'.</span></span>
7. <span data-ttu-id="cd195-116">Nel campo Nome digitare 'Messaggio di esempio fattura elettronica'.</span><span class="sxs-lookup"><span data-stu-id="cd195-116">In the Name field, type 'Electronic invoice sample message'.</span></span>
    * <span data-ttu-id="cd195-117">Messaggio di esempio fattura elettronica</span><span class="sxs-lookup"><span data-stu-id="cd195-117">Electronic invoice sample message</span></span>  
8. <span data-ttu-id="cd195-118">Nel campo Definizione modello dati immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="cd195-118">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="cd195-119">InvoiceCustomer</span><span class="sxs-lookup"><span data-stu-id="cd195-119">InvoiceCustomer</span></span>  
9. <span data-ttu-id="cd195-120">Fare clic su Crea configurazione.</span><span class="sxs-lookup"><span data-stu-id="cd195-120">Click Create configuration.</span></span>

## <a name="design-a-format-to-populate-attachments-into-generating-a-message-in-mime-format"></a><span data-ttu-id="cd195-121">Progettare un formato per popolare gli allegati nella generazione di un messaggio in formato MIME</span><span class="sxs-lookup"><span data-stu-id="cd195-121">Design a format to populate attachments into generating a message in MIME format</span></span>
1. <span data-ttu-id="cd195-122">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="cd195-122">Click Designer.</span></span>
2. <span data-ttu-id="cd195-123">Fare clic su Aggiungi radice per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="cd195-123">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="cd195-124">Nella struttura selezionare "XML\Elemento".</span><span class="sxs-lookup"><span data-stu-id="cd195-124">In the tree, select 'XML\Element'.</span></span>
4. <span data-ttu-id="cd195-125">Digitare 'Fattura' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="cd195-125">In the Name field, type 'Invoice'.</span></span>
    * <span data-ttu-id="cd195-126">Fattura</span><span class="sxs-lookup"><span data-stu-id="cd195-126">Invoice</span></span>  
5. <span data-ttu-id="cd195-127">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="cd195-127">Click OK.</span></span>
6. <span data-ttu-id="cd195-128">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="cd195-128">Click Add to open the drop dialog.</span></span>
7. <span data-ttu-id="cd195-129">Nella struttura selezionare "XML\Attributo".</span><span class="sxs-lookup"><span data-stu-id="cd195-129">In the tree, select 'XML\Attribute'.</span></span>
8. <span data-ttu-id="cd195-130">Digitare 'SalesOrder' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="cd195-130">In the Name field, type 'SalesOrder'.</span></span>
    * <span data-ttu-id="cd195-131">SalesOrder</span><span class="sxs-lookup"><span data-stu-id="cd195-131">SalesOrder</span></span>  
9. <span data-ttu-id="cd195-132">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="cd195-132">Click OK.</span></span>
10. <span data-ttu-id="cd195-133">Fare clic su Aggiungi attributo.</span><span class="sxs-lookup"><span data-stu-id="cd195-133">Click Add Attribute.</span></span>
11. <span data-ttu-id="cd195-134">Nel campo Nome digitare 'InvoiceNumber'.</span><span class="sxs-lookup"><span data-stu-id="cd195-134">In the Name field, type 'InvoiceNumber'.</span></span>
    * <span data-ttu-id="cd195-135">InvoiceNumber</span><span class="sxs-lookup"><span data-stu-id="cd195-135">InvoiceNumber</span></span>  
12. <span data-ttu-id="cd195-136">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="cd195-136">Click OK.</span></span>
13. <span data-ttu-id="cd195-137">Fare clic su Aggiungi attributo.</span><span class="sxs-lookup"><span data-stu-id="cd195-137">Click Add Attribute.</span></span>
14. <span data-ttu-id="cd195-138">Nel campo Nome digitare 'InvoiceAmount'.</span><span class="sxs-lookup"><span data-stu-id="cd195-138">In the Name field, type 'InvoiceAmount'.</span></span>
    * <span data-ttu-id="cd195-139">InvoiceAmount</span><span class="sxs-lookup"><span data-stu-id="cd195-139">InvoiceAmount</span></span>  
15. <span data-ttu-id="cd195-140">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="cd195-140">Click OK.</span></span>
16. <span data-ttu-id="cd195-141">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="cd195-141">Click Add to open the drop dialog.</span></span>
17. <span data-ttu-id="cd195-142">Nella struttura selezionare "XML\Elemento".</span><span class="sxs-lookup"><span data-stu-id="cd195-142">In the tree, select 'XML\Element'.</span></span>
18. <span data-ttu-id="cd195-143">Nel campo Nome digitare 'EnclosedDocs'.</span><span class="sxs-lookup"><span data-stu-id="cd195-143">In the Name field, type 'EnclosedDocs'.</span></span>
    * <span data-ttu-id="cd195-144">EnclosedDocs</span><span class="sxs-lookup"><span data-stu-id="cd195-144">EnclosedDocs</span></span>  
19. <span data-ttu-id="cd195-145">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="cd195-145">Click OK.</span></span>
20. <span data-ttu-id="cd195-146">Nella struttura selezionare 'Fattura\EnclosedDocs'.</span><span class="sxs-lookup"><span data-stu-id="cd195-146">In the tree, select 'Invoice\EnclosedDocs'.</span></span>
21. <span data-ttu-id="cd195-147">Fare clic su Aggiungi elemento.</span><span class="sxs-lookup"><span data-stu-id="cd195-147">Click Add Element.</span></span>
22. <span data-ttu-id="cd195-148">Nel campo Nome digitare 'Documento'.</span><span class="sxs-lookup"><span data-stu-id="cd195-148">In the Name field, type 'Document'.</span></span>
    * <span data-ttu-id="cd195-149">Documento</span><span class="sxs-lookup"><span data-stu-id="cd195-149">Document</span></span>  
23. <span data-ttu-id="cd195-150">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="cd195-150">Click OK.</span></span>
24. <span data-ttu-id="cd195-151">Nella struttura selezionare 'Fattura\EnclosedDocs\Documento'.</span><span class="sxs-lookup"><span data-stu-id="cd195-151">In the tree, select 'Invoice\EnclosedDocs\Document'.</span></span>
25. <span data-ttu-id="cd195-152">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="cd195-152">Click Add to open the drop dialog.</span></span>
26. <span data-ttu-id="cd195-153">Nella struttura selezionare "XML\Attributo".</span><span class="sxs-lookup"><span data-stu-id="cd195-153">In the tree, select 'XML\Attribute'.</span></span>
27. <span data-ttu-id="cd195-154">Nel campo Nome digitare 'FileName'.</span><span class="sxs-lookup"><span data-stu-id="cd195-154">In the Name field, type 'FileName'.</span></span>
    * <span data-ttu-id="cd195-155">FileName</span><span class="sxs-lookup"><span data-stu-id="cd195-155">FileName</span></span>  
28. <span data-ttu-id="cd195-156">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="cd195-156">Click OK.</span></span>
29. <span data-ttu-id="cd195-157">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="cd195-157">Click Add to open the drop dialog.</span></span>
30. <span data-ttu-id="cd195-158">Nella struttura selezionare "XML\Elemento".</span><span class="sxs-lookup"><span data-stu-id="cd195-158">In the tree, select 'XML\Element'.</span></span>
31. <span data-ttu-id="cd195-159">Digitare 'FileContent' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="cd195-159">In the Name field, type 'FileContent'.</span></span>
    * <span data-ttu-id="cd195-160">FileContent</span><span class="sxs-lookup"><span data-stu-id="cd195-160">FileContent</span></span>  
32. <span data-ttu-id="cd195-161">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="cd195-161">Click OK.</span></span>
33. <span data-ttu-id="cd195-162">Nella struttura selezionare 'Fattura\EnclosedDocs\Documento\FileContent'.</span><span class="sxs-lookup"><span data-stu-id="cd195-162">In the tree, select 'Invoice\EnclosedDocs\Document\FileContent'.</span></span>
34. <span data-ttu-id="cd195-163">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="cd195-163">Click Add to open the drop dialog.</span></span>
35. <span data-ttu-id="cd195-164">Nella struttura selezionare  'Testo\Base64'.</span><span class="sxs-lookup"><span data-stu-id="cd195-164">In the tree, select 'Text\Base64'.</span></span>
36. <span data-ttu-id="cd195-165">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="cd195-165">Click OK.</span></span>

## <a name="map-format-elements-to-data-model-as-data-source"></a><span data-ttu-id="cd195-166">Mappare gli elementi di formato al modello dati come origine dati</span><span class="sxs-lookup"><span data-stu-id="cd195-166">Map format elements to data model as data source</span></span>
1. <span data-ttu-id="cd195-167">Nella struttura selezionare 'Fattura\SalesOrder'.</span><span class="sxs-lookup"><span data-stu-id="cd195-167">In the tree, select 'Invoice\SalesOrder'.</span></span>
2. <span data-ttu-id="cd195-168">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="cd195-168">Click the Mapping tab.</span></span>
3. <span data-ttu-id="cd195-169">Nella struttura , espandere il "modello".</span><span class="sxs-lookup"><span data-stu-id="cd195-169">In the tree, expand 'model'.</span></span>
4. <span data-ttu-id="cd195-170">Nella struttura, selezionare 'modello\Numero ordine cliente(SalesId)'.</span><span class="sxs-lookup"><span data-stu-id="cd195-170">In the tree, select 'model\Sales order number(SalesId)'.</span></span>
5. <span data-ttu-id="cd195-171">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="cd195-171">Click Bind.</span></span>
6. <span data-ttu-id="cd195-172">Nella struttura selezionare 'Fattura\InvoiceNumber'.</span><span class="sxs-lookup"><span data-stu-id="cd195-172">In the tree, select 'Invoice\InvoiceNumber'.</span></span>
7. <span data-ttu-id="cd195-173">Nella struttura espandere 'modello\Fattura base(InvoiceBase)'.</span><span class="sxs-lookup"><span data-stu-id="cd195-173">In the tree, expand 'model\Base invoice(InvoiceBase)'.</span></span>
8. <span data-ttu-id="cd195-174">Nella struttura selezionare 'modello\Fattura base(InvoiceBase)\Numero fattura(Id)'.</span><span class="sxs-lookup"><span data-stu-id="cd195-174">In the tree, select 'model\Base invoice(InvoiceBase)\Invoice number(Id)'.</span></span>
9. <span data-ttu-id="cd195-175">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="cd195-175">Click Bind.</span></span>
10. <span data-ttu-id="cd195-176">Nella struttura selezionare 'Fattura\InvoiceAmount'.</span><span class="sxs-lookup"><span data-stu-id="cd195-176">In the tree, select 'Invoice\InvoiceAmount'.</span></span>
11. <span data-ttu-id="cd195-177">Nella struttura selezionare 'modello\Fattura base(InvoiceBase)\Importo fattura(Amount)'.</span><span class="sxs-lookup"><span data-stu-id="cd195-177">In the tree, select 'model\Base invoice(InvoiceBase)\Invoice amount(Amount)'.</span></span>
12. <span data-ttu-id="cd195-178">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="cd195-178">Click Bind.</span></span>
13. <span data-ttu-id="cd195-179">Nella struttura espandere 'modello\Allegati fattura'.</span><span class="sxs-lookup"><span data-stu-id="cd195-179">In the tree, expand 'model\Invoice attachments'.</span></span>
14. <span data-ttu-id="cd195-180">Nella struttura selezionare 'modello\Allegati fattura\Contenuto file'.</span><span class="sxs-lookup"><span data-stu-id="cd195-180">In the tree, select 'model\Invoice attachments\File content'.</span></span>
15. <span data-ttu-id="cd195-181">Nella struttura selezionare 'Fattura\EnclosedDocs\Documento\FileContent\Base64'.</span><span class="sxs-lookup"><span data-stu-id="cd195-181">In the tree, select 'Invoice\EnclosedDocs\Document\FileContent\Base64'.</span></span>
16. <span data-ttu-id="cd195-182">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="cd195-182">Click Bind.</span></span>
17. <span data-ttu-id="cd195-183">Nella struttura selezionare 'modello\Allegati fattura\Nome file'.</span><span class="sxs-lookup"><span data-stu-id="cd195-183">In the tree, select 'model\Invoice attachments\File name'.</span></span>
18. <span data-ttu-id="cd195-184">Nella struttura selezionare 'Fattura\EnclosedDocs\Documento\FileName'.</span><span class="sxs-lookup"><span data-stu-id="cd195-184">In the tree, select 'Invoice\EnclosedDocs\Document\FileName'.</span></span>
19. <span data-ttu-id="cd195-185">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="cd195-185">Click Bind.</span></span>
20. <span data-ttu-id="cd195-186">Nella struttura selezionare 'modello\Allegati fattura'.</span><span class="sxs-lookup"><span data-stu-id="cd195-186">In the tree, select 'model\Invoice attachments'.</span></span>
21. <span data-ttu-id="cd195-187">Nella struttura selezionare 'Fattura\EnclosedDocs\Documento'.</span><span class="sxs-lookup"><span data-stu-id="cd195-187">In the tree, select 'Invoice\EnclosedDocs\Document'.</span></span>
22. <span data-ttu-id="cd195-188">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="cd195-188">Click Bind.</span></span>
23. <span data-ttu-id="cd195-189">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="cd195-189">Click Save.</span></span>
24. <span data-ttu-id="cd195-190">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="cd195-190">Close the page.</span></span>


