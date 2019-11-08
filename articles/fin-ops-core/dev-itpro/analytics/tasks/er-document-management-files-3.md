---
title: ER Usare file di gestione documenti in output di formato (parte 3 - creare il formato)
description: I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che utilizzi i file (allegati) di gestione documenti nell'output della creazione di report elettronici.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 618fabc96bdfeb0c2b577aa686702d9f1257ed70
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550719"
---
# <a name="er-use-document-management-files-in-format-outputs-part-3---create-format"></a><span data-ttu-id="2e54e-103">ER Usare file di gestione documenti in output di formato (parte 3 - creare il formato)</span><span class="sxs-lookup"><span data-stu-id="2e54e-103">ER Use Document Management files in format outputs (Part 3 - Create format)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2e54e-104">I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che utilizzi i file (allegati) di gestione documenti nell'output della creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="2e54e-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="2e54e-105">Questi passaggi possono essere eseguiti in qualsiasi società.</span><span class="sxs-lookup"><span data-stu-id="2e54e-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="2e54e-106">Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi della procedura 'ER Usare i file di gestione documenti negli output di formato (parte 2: estendere il modello dati)'.</span><span class="sxs-lookup"><span data-stu-id="2e54e-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 2: Extend data model” procedure.</span></span>

<span data-ttu-id="2e54e-107">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="2e54e-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-format-to-process-invoices"></a><span data-ttu-id="2e54e-108">Creare un formato per l'elaborazione delle fatture</span><span class="sxs-lookup"><span data-stu-id="2e54e-108">Create a format to process invoices</span></span>
1. <span data-ttu-id="2e54e-109">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="2e54e-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="2e54e-110">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="2e54e-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="2e54e-111">Nella struttura espandere 'Modello fattura cliente'.</span><span class="sxs-lookup"><span data-stu-id="2e54e-111">In the tree, expand 'Customer invoice model'.</span></span>
4. <span data-ttu-id="2e54e-112">Nella struttura selezionare 'Modello fattura cliente\Modello fattura cliente (personalizzato)'.</span><span class="sxs-lookup"><span data-stu-id="2e54e-112">In the tree, select 'Customer invoice model\Customer invoice model (custom)'.</span></span>
    * <span data-ttu-id="2e54e-113">Creerete un formato per generare i messaggi elettronici con informazioni su tutti i file che sono stati allegati a un ordine cliente correlato a una fattura elaborata elettronicamente.</span><span class="sxs-lookup"><span data-stu-id="2e54e-113">You will create a format to generate electronic messages with information about any files that have been attached to a sales order that is related to an electronically processing invoice.</span></span>  
5. <span data-ttu-id="2e54e-114">Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .</span><span class="sxs-lookup"><span data-stu-id="2e54e-114">Click Create configuration to open the drop dialog.</span></span>
6. <span data-ttu-id="2e54e-115">Nel campo Nuovo immettere 'Formato basato sul modello dati Modello fattura cliente (personalizzato)'.</span><span class="sxs-lookup"><span data-stu-id="2e54e-115">In the New field, enter 'Format based on data model Customer invoice model (custom)'.</span></span>
7. <span data-ttu-id="2e54e-116">Nel campo Nome digitare 'Messaggio di esempio fattura elettronica'.</span><span class="sxs-lookup"><span data-stu-id="2e54e-116">In the Name field, type 'Electronic invoice sample message'.</span></span>
    * <span data-ttu-id="2e54e-117">Messaggio di esempio fattura elettronica</span><span class="sxs-lookup"><span data-stu-id="2e54e-117">Electronic invoice sample message</span></span>  
8. <span data-ttu-id="2e54e-118">Nel campo Definizione modello dati immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="2e54e-118">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="2e54e-119">InvoiceCustomer</span><span class="sxs-lookup"><span data-stu-id="2e54e-119">InvoiceCustomer</span></span>  
9. <span data-ttu-id="2e54e-120">Fare clic su Crea configurazione.</span><span class="sxs-lookup"><span data-stu-id="2e54e-120">Click Create configuration.</span></span>

## <a name="design-a-format-to-populate-attachments-into-generating-a-message-in-mime-format"></a><span data-ttu-id="2e54e-121">Progettare un formato per popolare gli allegati nella generazione di un messaggio in formato MIME</span><span class="sxs-lookup"><span data-stu-id="2e54e-121">Design a format to populate attachments into generating a message in MIME format</span></span>
1. <span data-ttu-id="2e54e-122">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="2e54e-122">Click Designer.</span></span>
2. <span data-ttu-id="2e54e-123">Fare clic su Aggiungi radice per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="2e54e-123">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="2e54e-124">Nella struttura selezionare "XML\Elemento".</span><span class="sxs-lookup"><span data-stu-id="2e54e-124">In the tree, select 'XML\Element'.</span></span>
4. <span data-ttu-id="2e54e-125">Digitare 'Fattura' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="2e54e-125">In the Name field, type 'Invoice'.</span></span>
    * <span data-ttu-id="2e54e-126">Fattura</span><span class="sxs-lookup"><span data-stu-id="2e54e-126">Invoice</span></span>  
5. <span data-ttu-id="2e54e-127">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2e54e-127">Click OK.</span></span>
6. <span data-ttu-id="2e54e-128">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="2e54e-128">Click Add to open the drop dialog.</span></span>
7. <span data-ttu-id="2e54e-129">Nella struttura selezionare "XML\Attributo".</span><span class="sxs-lookup"><span data-stu-id="2e54e-129">In the tree, select 'XML\Attribute'.</span></span>
8. <span data-ttu-id="2e54e-130">Digitare 'SalesOrder' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="2e54e-130">In the Name field, type 'SalesOrder'.</span></span>
    * <span data-ttu-id="2e54e-131">SalesOrder</span><span class="sxs-lookup"><span data-stu-id="2e54e-131">SalesOrder</span></span>  
9. <span data-ttu-id="2e54e-132">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2e54e-132">Click OK.</span></span>
10. <span data-ttu-id="2e54e-133">Fare clic su Aggiungi attributo.</span><span class="sxs-lookup"><span data-stu-id="2e54e-133">Click Add Attribute.</span></span>
11. <span data-ttu-id="2e54e-134">Nel campo Nome digitare 'InvoiceNumber'.</span><span class="sxs-lookup"><span data-stu-id="2e54e-134">In the Name field, type 'InvoiceNumber'.</span></span>
    * <span data-ttu-id="2e54e-135">InvoiceNumber</span><span class="sxs-lookup"><span data-stu-id="2e54e-135">InvoiceNumber</span></span>  
12. <span data-ttu-id="2e54e-136">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2e54e-136">Click OK.</span></span>
13. <span data-ttu-id="2e54e-137">Fare clic su Aggiungi attributo.</span><span class="sxs-lookup"><span data-stu-id="2e54e-137">Click Add Attribute.</span></span>
14. <span data-ttu-id="2e54e-138">Nel campo Nome digitare 'InvoiceAmount'.</span><span class="sxs-lookup"><span data-stu-id="2e54e-138">In the Name field, type 'InvoiceAmount'.</span></span>
    * <span data-ttu-id="2e54e-139">InvoiceAmount</span><span class="sxs-lookup"><span data-stu-id="2e54e-139">InvoiceAmount</span></span>  
15. <span data-ttu-id="2e54e-140">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2e54e-140">Click OK.</span></span>
16. <span data-ttu-id="2e54e-141">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="2e54e-141">Click Add to open the drop dialog.</span></span>
17. <span data-ttu-id="2e54e-142">Nella struttura selezionare "XML\Elemento".</span><span class="sxs-lookup"><span data-stu-id="2e54e-142">In the tree, select 'XML\Element'.</span></span>
18. <span data-ttu-id="2e54e-143">Nel campo Nome digitare 'EnclosedDocs'.</span><span class="sxs-lookup"><span data-stu-id="2e54e-143">In the Name field, type 'EnclosedDocs'.</span></span>
    * <span data-ttu-id="2e54e-144">EnclosedDocs</span><span class="sxs-lookup"><span data-stu-id="2e54e-144">EnclosedDocs</span></span>  
19. <span data-ttu-id="2e54e-145">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2e54e-145">Click OK.</span></span>
20. <span data-ttu-id="2e54e-146">Nella struttura selezionare 'Fattura\EnclosedDocs'.</span><span class="sxs-lookup"><span data-stu-id="2e54e-146">In the tree, select 'Invoice\EnclosedDocs'.</span></span>
21. <span data-ttu-id="2e54e-147">Fare clic su Aggiungi elemento.</span><span class="sxs-lookup"><span data-stu-id="2e54e-147">Click Add Element.</span></span>
22. <span data-ttu-id="2e54e-148">Nel campo Nome digitare 'Documento'.</span><span class="sxs-lookup"><span data-stu-id="2e54e-148">In the Name field, type 'Document'.</span></span>
    * <span data-ttu-id="2e54e-149">Documento</span><span class="sxs-lookup"><span data-stu-id="2e54e-149">Document</span></span>  
23. <span data-ttu-id="2e54e-150">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2e54e-150">Click OK.</span></span>
24. <span data-ttu-id="2e54e-151">Nella struttura selezionare 'Fattura\EnclosedDocs\Documento'.</span><span class="sxs-lookup"><span data-stu-id="2e54e-151">In the tree, select 'Invoice\EnclosedDocs\Document'.</span></span>
25. <span data-ttu-id="2e54e-152">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="2e54e-152">Click Add to open the drop dialog.</span></span>
26. <span data-ttu-id="2e54e-153">Nella struttura selezionare "XML\Attributo".</span><span class="sxs-lookup"><span data-stu-id="2e54e-153">In the tree, select 'XML\Attribute'.</span></span>
27. <span data-ttu-id="2e54e-154">Nel campo Nome digitare 'FileName'.</span><span class="sxs-lookup"><span data-stu-id="2e54e-154">In the Name field, type 'FileName'.</span></span>
    * <span data-ttu-id="2e54e-155">FileName</span><span class="sxs-lookup"><span data-stu-id="2e54e-155">FileName</span></span>  
28. <span data-ttu-id="2e54e-156">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2e54e-156">Click OK.</span></span>
29. <span data-ttu-id="2e54e-157">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="2e54e-157">Click Add to open the drop dialog.</span></span>
30. <span data-ttu-id="2e54e-158">Nella struttura selezionare "XML\Elemento".</span><span class="sxs-lookup"><span data-stu-id="2e54e-158">In the tree, select 'XML\Element'.</span></span>
31. <span data-ttu-id="2e54e-159">Digitare 'FileContent' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="2e54e-159">In the Name field, type 'FileContent'.</span></span>
    * <span data-ttu-id="2e54e-160">FileContent</span><span class="sxs-lookup"><span data-stu-id="2e54e-160">FileContent</span></span>  
32. <span data-ttu-id="2e54e-161">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2e54e-161">Click OK.</span></span>
33. <span data-ttu-id="2e54e-162">Nella struttura selezionare 'Fattura\EnclosedDocs\Documento\FileContent'.</span><span class="sxs-lookup"><span data-stu-id="2e54e-162">In the tree, select 'Invoice\EnclosedDocs\Document\FileContent'.</span></span>
34. <span data-ttu-id="2e54e-163">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="2e54e-163">Click Add to open the drop dialog.</span></span>
35. <span data-ttu-id="2e54e-164">Nella struttura selezionare  'Testo\Base64'.</span><span class="sxs-lookup"><span data-stu-id="2e54e-164">In the tree, select 'Text\Base64'.</span></span>
36. <span data-ttu-id="2e54e-165">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2e54e-165">Click OK.</span></span>

## <a name="map-format-elements-to-data-model-as-data-source"></a><span data-ttu-id="2e54e-166">Mappare gli elementi di formato al modello dati come origine dati</span><span class="sxs-lookup"><span data-stu-id="2e54e-166">Map format elements to data model as data source</span></span>
1. <span data-ttu-id="2e54e-167">Nella struttura selezionare 'Fattura\SalesOrder'.</span><span class="sxs-lookup"><span data-stu-id="2e54e-167">In the tree, select 'Invoice\SalesOrder'.</span></span>
2. <span data-ttu-id="2e54e-168">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="2e54e-168">Click the Mapping tab.</span></span>
3. <span data-ttu-id="2e54e-169">Nella struttura , espandere il "modello".</span><span class="sxs-lookup"><span data-stu-id="2e54e-169">In the tree, expand 'model'.</span></span>
4. <span data-ttu-id="2e54e-170">Nella struttura, selezionare 'modello\Numero ordine cliente(SalesId)'.</span><span class="sxs-lookup"><span data-stu-id="2e54e-170">In the tree, select 'model\Sales order number(SalesId)'.</span></span>
5. <span data-ttu-id="2e54e-171">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="2e54e-171">Click Bind.</span></span>
6. <span data-ttu-id="2e54e-172">Nella struttura selezionare 'Fattura\InvoiceNumber'.</span><span class="sxs-lookup"><span data-stu-id="2e54e-172">In the tree, select 'Invoice\InvoiceNumber'.</span></span>
7. <span data-ttu-id="2e54e-173">Nella struttura espandere 'modello\Fattura base(InvoiceBase)'.</span><span class="sxs-lookup"><span data-stu-id="2e54e-173">In the tree, expand 'model\Base invoice(InvoiceBase)'.</span></span>
8. <span data-ttu-id="2e54e-174">Nella struttura selezionare 'modello\Fattura base(InvoiceBase)\Numero fattura(Id)'.</span><span class="sxs-lookup"><span data-stu-id="2e54e-174">In the tree, select 'model\Base invoice(InvoiceBase)\Invoice number(Id)'.</span></span>
9. <span data-ttu-id="2e54e-175">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="2e54e-175">Click Bind.</span></span>
10. <span data-ttu-id="2e54e-176">Nella struttura selezionare 'Fattura\InvoiceAmount'.</span><span class="sxs-lookup"><span data-stu-id="2e54e-176">In the tree, select 'Invoice\InvoiceAmount'.</span></span>
11. <span data-ttu-id="2e54e-177">Nella struttura selezionare 'modello\Fattura base(InvoiceBase)\Importo fattura(Amount)'.</span><span class="sxs-lookup"><span data-stu-id="2e54e-177">In the tree, select 'model\Base invoice(InvoiceBase)\Invoice amount(Amount)'.</span></span>
12. <span data-ttu-id="2e54e-178">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="2e54e-178">Click Bind.</span></span>
13. <span data-ttu-id="2e54e-179">Nella struttura espandere 'modello\Allegati fattura'.</span><span class="sxs-lookup"><span data-stu-id="2e54e-179">In the tree, expand 'model\Invoice attachments'.</span></span>
14. <span data-ttu-id="2e54e-180">Nella struttura selezionare 'modello\Allegati fattura\Contenuto file'.</span><span class="sxs-lookup"><span data-stu-id="2e54e-180">In the tree, select 'model\Invoice attachments\File content'.</span></span>
15. <span data-ttu-id="2e54e-181">Nella struttura selezionare 'Fattura\EnclosedDocs\Documento\FileContent\Base64'.</span><span class="sxs-lookup"><span data-stu-id="2e54e-181">In the tree, select 'Invoice\EnclosedDocs\Document\FileContent\Base64'.</span></span>
16. <span data-ttu-id="2e54e-182">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="2e54e-182">Click Bind.</span></span>
17. <span data-ttu-id="2e54e-183">Nella struttura selezionare 'modello\Allegati fattura\Nome file'.</span><span class="sxs-lookup"><span data-stu-id="2e54e-183">In the tree, select 'model\Invoice attachments\File name'.</span></span>
18. <span data-ttu-id="2e54e-184">Nella struttura selezionare 'Fattura\EnclosedDocs\Documento\FileName'.</span><span class="sxs-lookup"><span data-stu-id="2e54e-184">In the tree, select 'Invoice\EnclosedDocs\Document\FileName'.</span></span>
19. <span data-ttu-id="2e54e-185">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="2e54e-185">Click Bind.</span></span>
20. <span data-ttu-id="2e54e-186">Nella struttura selezionare 'modello\Allegati fattura'.</span><span class="sxs-lookup"><span data-stu-id="2e54e-186">In the tree, select 'model\Invoice attachments'.</span></span>
21. <span data-ttu-id="2e54e-187">Nella struttura selezionare 'Fattura\EnclosedDocs\Documento'.</span><span class="sxs-lookup"><span data-stu-id="2e54e-187">In the tree, select 'Invoice\EnclosedDocs\Document'.</span></span>
22. <span data-ttu-id="2e54e-188">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="2e54e-188">Click Bind.</span></span>
23. <span data-ttu-id="2e54e-189">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="2e54e-189">Click Save.</span></span>
24. <span data-ttu-id="2e54e-190">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2e54e-190">Close the page.</span></span>

