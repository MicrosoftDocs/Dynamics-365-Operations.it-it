---
title: ER Usare file di gestione documenti in output di formato (parte 3 - creare il formato)
description: In questo argomento viene descritto come configurare un formato di reporting elettronico per utilizzare i file di gestione dei documenti nell'output ER. (Parte 3)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1ec1ebc15cd980734aebec63d6758404868c1e36
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559751"
---
# <a name="er-use-document-management-files-in-format-outputs-part-3---create-format"></a><span data-ttu-id="82408-104">ER Usare file di gestione documenti in output di formato (parte 3 - creare il formato)</span><span class="sxs-lookup"><span data-stu-id="82408-104">ER Use Document Management files in format outputs (Part 3 - Create format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="82408-105">I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che utilizzi i file (allegati) di gestione documenti nell'output della creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="82408-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="82408-106">Questi passaggi possono essere eseguiti in qualsiasi società.</span><span class="sxs-lookup"><span data-stu-id="82408-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="82408-107">Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi della procedura "ER Usare i file di gestione documenti negli output di formato (parte 2: estendere il modello dati)".</span><span class="sxs-lookup"><span data-stu-id="82408-107">To complete these steps, you must first complete the steps in the "ER Use Document Management files in format outputs (Part 2: Extend data model" procedure.</span></span>

<span data-ttu-id="82408-108">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="82408-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-format-to-process-invoices"></a><span data-ttu-id="82408-109">Creare un formato per l'elaborazione delle fatture</span><span class="sxs-lookup"><span data-stu-id="82408-109">Create a format to process invoices</span></span>
1. <span data-ttu-id="82408-110">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="82408-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="82408-111">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="82408-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="82408-112">Nella struttura espandere 'Modello fattura cliente'.</span><span class="sxs-lookup"><span data-stu-id="82408-112">In the tree, expand 'Customer invoice model'.</span></span>
4. <span data-ttu-id="82408-113">Nella struttura selezionare 'Modello fattura cliente\Modello fattura cliente (personalizzato)'.</span><span class="sxs-lookup"><span data-stu-id="82408-113">In the tree, select 'Customer invoice model\Customer invoice model (custom)'.</span></span>
    * <span data-ttu-id="82408-114">Creerete un formato per generare i messaggi elettronici con informazioni su tutti i file che sono stati allegati a un ordine cliente correlato a una fattura elaborata elettronicamente.</span><span class="sxs-lookup"><span data-stu-id="82408-114">You will create a format to generate electronic messages with information about any files that have been attached to a sales order that is related to an electronically processing invoice.</span></span>  
5. <span data-ttu-id="82408-115">Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .</span><span class="sxs-lookup"><span data-stu-id="82408-115">Click Create configuration to open the drop dialog.</span></span>
6. <span data-ttu-id="82408-116">Nel campo Nuovo immettere 'Formato basato sul modello dati Modello fattura cliente (personalizzato)'.</span><span class="sxs-lookup"><span data-stu-id="82408-116">In the New field, enter 'Format based on data model Customer invoice model (custom)'.</span></span>
7. <span data-ttu-id="82408-117">Nel campo Nome digitare 'Messaggio di esempio fattura elettronica'.</span><span class="sxs-lookup"><span data-stu-id="82408-117">In the Name field, type 'Electronic invoice sample message'.</span></span>
    * <span data-ttu-id="82408-118">Messaggio di esempio fattura elettronica</span><span class="sxs-lookup"><span data-stu-id="82408-118">Electronic invoice sample message</span></span>  
8. <span data-ttu-id="82408-119">Nel campo Definizione modello dati immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="82408-119">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="82408-120">InvoiceCustomer</span><span class="sxs-lookup"><span data-stu-id="82408-120">InvoiceCustomer</span></span>  
9. <span data-ttu-id="82408-121">Fare clic su Crea configurazione.</span><span class="sxs-lookup"><span data-stu-id="82408-121">Click Create configuration.</span></span>

## <a name="design-a-format-to-populate-attachments-into-generating-a-message-in-mime-format"></a><span data-ttu-id="82408-122">Progettare un formato per popolare gli allegati nella generazione di un messaggio in formato MIME</span><span class="sxs-lookup"><span data-stu-id="82408-122">Design a format to populate attachments into generating a message in MIME format</span></span>
1. <span data-ttu-id="82408-123">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="82408-123">Click Designer.</span></span>
2. <span data-ttu-id="82408-124">Fare clic su Aggiungi radice per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="82408-124">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="82408-125">Nella struttura selezionare "XML\Elemento".</span><span class="sxs-lookup"><span data-stu-id="82408-125">In the tree, select 'XML\Element'.</span></span>
4. <span data-ttu-id="82408-126">Digitare 'Fattura' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="82408-126">In the Name field, type 'Invoice'.</span></span>
    * <span data-ttu-id="82408-127">Fattura</span><span class="sxs-lookup"><span data-stu-id="82408-127">Invoice</span></span>  
5. <span data-ttu-id="82408-128">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="82408-128">Click OK.</span></span>
6. <span data-ttu-id="82408-129">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="82408-129">Click Add to open the drop dialog.</span></span>
7. <span data-ttu-id="82408-130">Nella struttura selezionare "XML\Attributo".</span><span class="sxs-lookup"><span data-stu-id="82408-130">In the tree, select 'XML\Attribute'.</span></span>
8. <span data-ttu-id="82408-131">Digitare 'SalesOrder' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="82408-131">In the Name field, type 'SalesOrder'.</span></span>
    * <span data-ttu-id="82408-132">SalesOrder</span><span class="sxs-lookup"><span data-stu-id="82408-132">SalesOrder</span></span>  
9. <span data-ttu-id="82408-133">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="82408-133">Click OK.</span></span>
10. <span data-ttu-id="82408-134">Fare clic su Aggiungi attributo.</span><span class="sxs-lookup"><span data-stu-id="82408-134">Click Add Attribute.</span></span>
11. <span data-ttu-id="82408-135">Nel campo Nome digitare 'InvoiceNumber'.</span><span class="sxs-lookup"><span data-stu-id="82408-135">In the Name field, type 'InvoiceNumber'.</span></span>
    * <span data-ttu-id="82408-136">InvoiceNumber</span><span class="sxs-lookup"><span data-stu-id="82408-136">InvoiceNumber</span></span>  
12. <span data-ttu-id="82408-137">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="82408-137">Click OK.</span></span>
13. <span data-ttu-id="82408-138">Fare clic su Aggiungi attributo.</span><span class="sxs-lookup"><span data-stu-id="82408-138">Click Add Attribute.</span></span>
14. <span data-ttu-id="82408-139">Nel campo Nome digitare 'InvoiceAmount'.</span><span class="sxs-lookup"><span data-stu-id="82408-139">In the Name field, type 'InvoiceAmount'.</span></span>
    * <span data-ttu-id="82408-140">InvoiceAmount</span><span class="sxs-lookup"><span data-stu-id="82408-140">InvoiceAmount</span></span>  
15. <span data-ttu-id="82408-141">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="82408-141">Click OK.</span></span>
16. <span data-ttu-id="82408-142">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="82408-142">Click Add to open the drop dialog.</span></span>
17. <span data-ttu-id="82408-143">Nella struttura selezionare "XML\Elemento".</span><span class="sxs-lookup"><span data-stu-id="82408-143">In the tree, select 'XML\Element'.</span></span>
18. <span data-ttu-id="82408-144">Nel campo Nome digitare 'EnclosedDocs'.</span><span class="sxs-lookup"><span data-stu-id="82408-144">In the Name field, type 'EnclosedDocs'.</span></span>
    * <span data-ttu-id="82408-145">EnclosedDocs</span><span class="sxs-lookup"><span data-stu-id="82408-145">EnclosedDocs</span></span>  
19. <span data-ttu-id="82408-146">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="82408-146">Click OK.</span></span>
20. <span data-ttu-id="82408-147">Nella struttura selezionare 'Fattura\EnclosedDocs'.</span><span class="sxs-lookup"><span data-stu-id="82408-147">In the tree, select 'Invoice\EnclosedDocs'.</span></span>
21. <span data-ttu-id="82408-148">Fare clic su Aggiungi elemento.</span><span class="sxs-lookup"><span data-stu-id="82408-148">Click Add Element.</span></span>
22. <span data-ttu-id="82408-149">Nel campo Nome digitare 'Documento'.</span><span class="sxs-lookup"><span data-stu-id="82408-149">In the Name field, type 'Document'.</span></span>
    * <span data-ttu-id="82408-150">Documento</span><span class="sxs-lookup"><span data-stu-id="82408-150">Document</span></span>  
23. <span data-ttu-id="82408-151">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="82408-151">Click OK.</span></span>
24. <span data-ttu-id="82408-152">Nella struttura selezionare 'Fattura\EnclosedDocs\Documento'.</span><span class="sxs-lookup"><span data-stu-id="82408-152">In the tree, select 'Invoice\EnclosedDocs\Document'.</span></span>
25. <span data-ttu-id="82408-153">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="82408-153">Click Add to open the drop dialog.</span></span>
26. <span data-ttu-id="82408-154">Nella struttura selezionare "XML\Attributo".</span><span class="sxs-lookup"><span data-stu-id="82408-154">In the tree, select 'XML\Attribute'.</span></span>
27. <span data-ttu-id="82408-155">Nel campo Nome digitare 'FileName'.</span><span class="sxs-lookup"><span data-stu-id="82408-155">In the Name field, type 'FileName'.</span></span>
    * <span data-ttu-id="82408-156">FileName</span><span class="sxs-lookup"><span data-stu-id="82408-156">FileName</span></span>  
28. <span data-ttu-id="82408-157">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="82408-157">Click OK.</span></span>
29. <span data-ttu-id="82408-158">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="82408-158">Click Add to open the drop dialog.</span></span>
30. <span data-ttu-id="82408-159">Nella struttura selezionare "XML\Elemento".</span><span class="sxs-lookup"><span data-stu-id="82408-159">In the tree, select 'XML\Element'.</span></span>
31. <span data-ttu-id="82408-160">Digitare 'FileContent' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="82408-160">In the Name field, type 'FileContent'.</span></span>
    * <span data-ttu-id="82408-161">FileContent</span><span class="sxs-lookup"><span data-stu-id="82408-161">FileContent</span></span>  
32. <span data-ttu-id="82408-162">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="82408-162">Click OK.</span></span>
33. <span data-ttu-id="82408-163">Nella struttura selezionare 'Fattura\EnclosedDocs\Documento\FileContent'.</span><span class="sxs-lookup"><span data-stu-id="82408-163">In the tree, select 'Invoice\EnclosedDocs\Document\FileContent'.</span></span>
34. <span data-ttu-id="82408-164">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="82408-164">Click Add to open the drop dialog.</span></span>
35. <span data-ttu-id="82408-165">Nella struttura selezionare  'Testo\Base64'.</span><span class="sxs-lookup"><span data-stu-id="82408-165">In the tree, select 'Text\Base64'.</span></span>
36. <span data-ttu-id="82408-166">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="82408-166">Click OK.</span></span>

## <a name="map-format-elements-to-data-model-as-data-source"></a><span data-ttu-id="82408-167">Mappare gli elementi di formato al modello dati come origine dati</span><span class="sxs-lookup"><span data-stu-id="82408-167">Map format elements to data model as data source</span></span>
1. <span data-ttu-id="82408-168">Nella struttura selezionare 'Fattura\SalesOrder'.</span><span class="sxs-lookup"><span data-stu-id="82408-168">In the tree, select 'Invoice\SalesOrder'.</span></span>
2. <span data-ttu-id="82408-169">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="82408-169">Click the Mapping tab.</span></span>
3. <span data-ttu-id="82408-170">Nella struttura , espandere il "modello".</span><span class="sxs-lookup"><span data-stu-id="82408-170">In the tree, expand 'model'.</span></span>
4. <span data-ttu-id="82408-171">Nella struttura, selezionare 'modello\Numero ordine cliente(SalesId)'.</span><span class="sxs-lookup"><span data-stu-id="82408-171">In the tree, select 'model\Sales order number(SalesId)'.</span></span>
5. <span data-ttu-id="82408-172">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="82408-172">Click Bind.</span></span>
6. <span data-ttu-id="82408-173">Nella struttura selezionare 'Fattura\InvoiceNumber'.</span><span class="sxs-lookup"><span data-stu-id="82408-173">In the tree, select 'Invoice\InvoiceNumber'.</span></span>
7. <span data-ttu-id="82408-174">Nella struttura espandere 'modello\Fattura base(InvoiceBase)'.</span><span class="sxs-lookup"><span data-stu-id="82408-174">In the tree, expand 'model\Base invoice(InvoiceBase)'.</span></span>
8. <span data-ttu-id="82408-175">Nella struttura selezionare 'modello\Fattura base(InvoiceBase)\Numero fattura(Id)'.</span><span class="sxs-lookup"><span data-stu-id="82408-175">In the tree, select 'model\Base invoice(InvoiceBase)\Invoice number(Id)'.</span></span>
9. <span data-ttu-id="82408-176">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="82408-176">Click Bind.</span></span>
10. <span data-ttu-id="82408-177">Nella struttura selezionare 'Fattura\InvoiceAmount'.</span><span class="sxs-lookup"><span data-stu-id="82408-177">In the tree, select 'Invoice\InvoiceAmount'.</span></span>
11. <span data-ttu-id="82408-178">Nella struttura selezionare 'modello\Fattura base(InvoiceBase)\Importo fattura(Amount)'.</span><span class="sxs-lookup"><span data-stu-id="82408-178">In the tree, select 'model\Base invoice(InvoiceBase)\Invoice amount(Amount)'.</span></span>
12. <span data-ttu-id="82408-179">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="82408-179">Click Bind.</span></span>
13. <span data-ttu-id="82408-180">Nella struttura espandere 'modello\Allegati fattura'.</span><span class="sxs-lookup"><span data-stu-id="82408-180">In the tree, expand 'model\Invoice attachments'.</span></span>
14. <span data-ttu-id="82408-181">Nella struttura selezionare 'modello\Allegati fattura\Contenuto file'.</span><span class="sxs-lookup"><span data-stu-id="82408-181">In the tree, select 'model\Invoice attachments\File content'.</span></span>
15. <span data-ttu-id="82408-182">Nella struttura selezionare 'Fattura\EnclosedDocs\Documento\FileContent\Base64'.</span><span class="sxs-lookup"><span data-stu-id="82408-182">In the tree, select 'Invoice\EnclosedDocs\Document\FileContent\Base64'.</span></span>
16. <span data-ttu-id="82408-183">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="82408-183">Click Bind.</span></span>
17. <span data-ttu-id="82408-184">Nella struttura selezionare 'modello\Allegati fattura\Nome file'.</span><span class="sxs-lookup"><span data-stu-id="82408-184">In the tree, select 'model\Invoice attachments\File name'.</span></span>
18. <span data-ttu-id="82408-185">Nella struttura selezionare 'Fattura\EnclosedDocs\Documento\FileName'.</span><span class="sxs-lookup"><span data-stu-id="82408-185">In the tree, select 'Invoice\EnclosedDocs\Document\FileName'.</span></span>
19. <span data-ttu-id="82408-186">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="82408-186">Click Bind.</span></span>
20. <span data-ttu-id="82408-187">Nella struttura selezionare 'modello\Allegati fattura'.</span><span class="sxs-lookup"><span data-stu-id="82408-187">In the tree, select 'model\Invoice attachments'.</span></span>
21. <span data-ttu-id="82408-188">Nella struttura selezionare 'Fattura\EnclosedDocs\Documento'.</span><span class="sxs-lookup"><span data-stu-id="82408-188">In the tree, select 'Invoice\EnclosedDocs\Document'.</span></span>
22. <span data-ttu-id="82408-189">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="82408-189">Click Bind.</span></span>
23. <span data-ttu-id="82408-190">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="82408-190">Click Save.</span></span>
24. <span data-ttu-id="82408-191">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="82408-191">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]