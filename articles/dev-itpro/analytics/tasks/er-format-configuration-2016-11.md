--- 
title: ER Creare una configurazione formato (novembre 2016)
description: "I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare una configurazione di formato per la creazione di report elettronici."
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 803ed4a1018d344f1b40fa1f2338fc066e784c3c
ms.contentlocale: it-it
ms.lasthandoff: 10/16/2018

---
# <a name="er-create-a-format-configuration-november-2016"></a><span data-ttu-id="2edc2-103">ER Creare una configurazione formato (novembre 2016)</span><span class="sxs-lookup"><span data-stu-id="2edc2-103">ER Create a format configuration (November 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2edc2-104">I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare una configurazione di formato per la creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="2edc2-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a format configuration for Electronic reporting (ER).</span></span> <span data-ttu-id="2edc2-105">Tale configurazione di formato definirà il formato dei documenti elettronici utilizzati per l'elaborazione dei pagamenti.</span><span class="sxs-lookup"><span data-stu-id="2edc2-105">This format configuration will define the format of electronic documents that are used for processing payments.</span></span> <span data-ttu-id="2edc2-106">In questo esempio verrà creata una configurazione di formato per la società di esempio Litware, Inc. Per completare questi passaggi, è necessario aver completato prima i passaggi della procedura "Mappare il modello alle origini dati selezionate".</span><span class="sxs-lookup"><span data-stu-id="2edc2-106">In this example, you will create a format configuration for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the “Map model to selected datasources” procedure.</span></span>


## <a name="create-a-new-format-configuration"></a><span data-ttu-id="2edc2-107">Creare una nuova configurazione di formato</span><span class="sxs-lookup"><span data-stu-id="2edc2-107">Create a new format configuration</span></span>
1. <span data-ttu-id="2edc2-108">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="2edc2-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="2edc2-109">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="2edc2-109">Click Reporting configurations.</span></span>
3. <span data-ttu-id="2edc2-110">Nella struttura selezionare "Pagamenti (modello semplificato)".</span><span class="sxs-lookup"><span data-stu-id="2edc2-110">In the tree, select 'Payments (simplified model)'.</span></span>
4. <span data-ttu-id="2edc2-111">Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .</span><span class="sxs-lookup"><span data-stu-id="2edc2-111">Click Create configuration to open the drop dialog.</span></span>
5. <span data-ttu-id="2edc2-112">Nel campo Nuovo immettere "Formato in base al modello dati PaymentModel".</span><span class="sxs-lookup"><span data-stu-id="2edc2-112">In the New field, enter 'Format based on data model PaymentModel'.</span></span>
6. <span data-ttu-id="2edc2-113">Nel campo Nome digitare "BACS (fittizio per il Regno Unito)".</span><span class="sxs-lookup"><span data-stu-id="2edc2-113">In the Name field, type 'BACS (UK fictitious)'.</span></span>
    * <span data-ttu-id="2edc2-114">BACS (fittizio per il Regno Unito)</span><span class="sxs-lookup"><span data-stu-id="2edc2-114">BACS (UK fictitious)</span></span>  
7. <span data-ttu-id="2edc2-115">Nel campo Descrizione digitare "Formato di pagamento fornitore BACS (fittizio per il Regno Unito)".</span><span class="sxs-lookup"><span data-stu-id="2edc2-115">In the Description field, type 'BACS vendor payment format (UK fictitious)'.</span></span>
    * <span data-ttu-id="2edc2-116">Formato di pagamento fornitore BACS (fittizio per il Regno Unito)</span><span class="sxs-lookup"><span data-stu-id="2edc2-116">BACS vendor payment format (UK fictitious)</span></span>  
    * <span data-ttu-id="2edc2-117">Il provider di configurazione attiva viene inserito automaticamente in questo punto.</span><span class="sxs-lookup"><span data-stu-id="2edc2-117">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="2edc2-118">Tale provider potrà gestire la configurazione.</span><span class="sxs-lookup"><span data-stu-id="2edc2-118">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="2edc2-119">Altri provider possono utilizzare la configurazione, ma non potranno gestirla.</span><span class="sxs-lookup"><span data-stu-id="2edc2-119">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
    * <span data-ttu-id="2edc2-120">È possibile definire un formato specifico del documento elettronico.</span><span class="sxs-lookup"><span data-stu-id="2edc2-120">A particular format of electronic document can be defined.</span></span> <span data-ttu-id="2edc2-121">Lasciare vuoto il campo se si desidera selezionare un formato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2edc2-121">Leave this field blank if you want to select a format at run-time.</span></span>  
8. <span data-ttu-id="2edc2-122">Nel campo Definizione modello dati immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="2edc2-122">In the Data model definition field, enter or select a value.</span></span>
9. <span data-ttu-id="2edc2-123">Fare clic su Crea configurazione.</span><span class="sxs-lookup"><span data-stu-id="2edc2-123">Click Create configuration.</span></span>
    * <span data-ttu-id="2edc2-124">È stata creata una nuova configurazione.</span><span class="sxs-lookup"><span data-stu-id="2edc2-124">A new configuration has been created.</span></span> <span data-ttu-id="2edc2-125">La versione bozza può essere utilizzata per archiviare il formato di progettazione per gestire i documenti elettronici.</span><span class="sxs-lookup"><span data-stu-id="2edc2-125">The draft version can be used to store the design format for managing electronic documents.</span></span>  

## <a name="design-format-of-electronic-document"></a><span data-ttu-id="2edc2-126">Formato di progettazione del documento elettronico</span><span class="sxs-lookup"><span data-stu-id="2edc2-126">Design format of electronic document</span></span>
1. <span data-ttu-id="2edc2-127">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="2edc2-127">Click Designer.</span></span>
2. <span data-ttu-id="2edc2-128">Fare clic su Aggiungi radice per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="2edc2-128">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="2edc2-129">Nella struttura selezionare "Comune\File".</span><span class="sxs-lookup"><span data-stu-id="2edc2-129">In the tree, select 'Common\File'.</span></span>
4. <span data-ttu-id="2edc2-130">Nel campo Nome digitare "XML".</span><span class="sxs-lookup"><span data-stu-id="2edc2-130">In the Name field, type 'Xml'.</span></span>
    * <span data-ttu-id="2edc2-131">XML</span><span class="sxs-lookup"><span data-stu-id="2edc2-131">Xml</span></span>  
5. <span data-ttu-id="2edc2-132">Nel campo Codifica digitare "UTF-8".</span><span class="sxs-lookup"><span data-stu-id="2edc2-132">In the Encoding field, type 'UTF-8'.</span></span>
    * <span data-ttu-id="2edc2-133">UTF-8</span><span class="sxs-lookup"><span data-stu-id="2edc2-133">UTF-8</span></span>  
6. <span data-ttu-id="2edc2-134">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2edc2-134">Click OK.</span></span>
7. <span data-ttu-id="2edc2-135">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="2edc2-135">Click Add to open the drop dialog.</span></span>
8. <span data-ttu-id="2edc2-136">Nella struttura selezionare "XML\Elemento".</span><span class="sxs-lookup"><span data-stu-id="2edc2-136">In the tree, select 'XML\Element'.</span></span>
9. <span data-ttu-id="2edc2-137">Nel campo Nome digitare "Messaggio".</span><span class="sxs-lookup"><span data-stu-id="2edc2-137">In the Name field, type 'Message'.</span></span>
    * <span data-ttu-id="2edc2-138">Messaggio</span><span class="sxs-lookup"><span data-stu-id="2edc2-138">Message</span></span>  
10. <span data-ttu-id="2edc2-139">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2edc2-139">Click OK.</span></span>
11. <span data-ttu-id="2edc2-140">Nella struttura selezionare 'Xml\Messaggio'.</span><span class="sxs-lookup"><span data-stu-id="2edc2-140">In the tree, select 'Xml\Message'.</span></span>
12. <span data-ttu-id="2edc2-141">Fare clic su Aggiungi elemento.</span><span class="sxs-lookup"><span data-stu-id="2edc2-141">Click Add Element.</span></span>
13. <span data-ttu-id="2edc2-142">Nel campo Nome digitare "ProcessingDate".</span><span class="sxs-lookup"><span data-stu-id="2edc2-142">In the Name field, type 'ProcessingDate'.</span></span>
    * <span data-ttu-id="2edc2-143">ProcessingDate</span><span class="sxs-lookup"><span data-stu-id="2edc2-143">ProcessingDate</span></span>  
14. <span data-ttu-id="2edc2-144">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2edc2-144">Click OK.</span></span>
15. <span data-ttu-id="2edc2-145">Fare clic su Aggiungi elemento.</span><span class="sxs-lookup"><span data-stu-id="2edc2-145">Click Add Element.</span></span>
16. <span data-ttu-id="2edc2-146">Nel campo Nome digitare "MessageId".</span><span class="sxs-lookup"><span data-stu-id="2edc2-146">In the Name field, type 'MessageId'.</span></span>
    * <span data-ttu-id="2edc2-147">MessageId</span><span class="sxs-lookup"><span data-stu-id="2edc2-147">MessageId</span></span>  
17. <span data-ttu-id="2edc2-148">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2edc2-148">Click OK.</span></span>
18. <span data-ttu-id="2edc2-149">Fare clic su Aggiungi elemento.</span><span class="sxs-lookup"><span data-stu-id="2edc2-149">Click Add Element.</span></span>
19. <span data-ttu-id="2edc2-150">Nel campo Nome digitare "Pagamenti".</span><span class="sxs-lookup"><span data-stu-id="2edc2-150">In the Name field, type 'Payments'.</span></span>
    * <span data-ttu-id="2edc2-151">Pagamenti</span><span class="sxs-lookup"><span data-stu-id="2edc2-151">Payments</span></span>  
20. <span data-ttu-id="2edc2-152">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2edc2-152">Click OK.</span></span>
21. <span data-ttu-id="2edc2-153">Nella struttura selezionare 'Xml\Messaggio\Pagamenti'.</span><span class="sxs-lookup"><span data-stu-id="2edc2-153">In the tree, select 'Xml\Message\Payments'.</span></span>
22. <span data-ttu-id="2edc2-154">Fare clic su Aggiungi elemento.</span><span class="sxs-lookup"><span data-stu-id="2edc2-154">Click Add Element.</span></span>
23. <span data-ttu-id="2edc2-155">Nel campo Nome digitare "Articolo".</span><span class="sxs-lookup"><span data-stu-id="2edc2-155">In the Name field, type 'Item'.</span></span>
    * <span data-ttu-id="2edc2-156">Articolo</span><span class="sxs-lookup"><span data-stu-id="2edc2-156">Item</span></span>  
24. <span data-ttu-id="2edc2-157">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2edc2-157">Click OK.</span></span>
25. <span data-ttu-id="2edc2-158">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo'.</span><span class="sxs-lookup"><span data-stu-id="2edc2-158">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
26. <span data-ttu-id="2edc2-159">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="2edc2-159">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="2edc2-160">Nella struttura selezionare "XML\Attributo".</span><span class="sxs-lookup"><span data-stu-id="2edc2-160">In the tree, select 'XML\Attribute'.</span></span>
28. <span data-ttu-id="2edc2-161">Nel campo Nome digitare "ID".</span><span class="sxs-lookup"><span data-stu-id="2edc2-161">In the Name field, type 'Id'.</span></span>
    * <span data-ttu-id="2edc2-162">ID</span><span class="sxs-lookup"><span data-stu-id="2edc2-162">Id</span></span>  
29. <span data-ttu-id="2edc2-163">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2edc2-163">Click OK.</span></span>
30. <span data-ttu-id="2edc2-164">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="2edc2-164">Click Add to open the drop dialog.</span></span>
31. <span data-ttu-id="2edc2-165">Nella struttura selezionare "XML\Elemento".</span><span class="sxs-lookup"><span data-stu-id="2edc2-165">In the tree, select 'XML\Element'.</span></span>
32. <span data-ttu-id="2edc2-166">Nel campo Nome digitare "Fornitore".</span><span class="sxs-lookup"><span data-stu-id="2edc2-166">In the Name field, type 'Vendor'.</span></span>
    * <span data-ttu-id="2edc2-167">Fornitore</span><span class="sxs-lookup"><span data-stu-id="2edc2-167">Vendor</span></span>  
33. <span data-ttu-id="2edc2-168">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2edc2-168">Click OK.</span></span>
34. <span data-ttu-id="2edc2-169">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Fornitore'.</span><span class="sxs-lookup"><span data-stu-id="2edc2-169">In the tree, select 'Xml\Message\Payments\Item\Vendor'.</span></span>
35. <span data-ttu-id="2edc2-170">Fare clic su Aggiungi elemento.</span><span class="sxs-lookup"><span data-stu-id="2edc2-170">Click Add Element.</span></span>
36. <span data-ttu-id="2edc2-171">Nel campo Nome digitare "Nome".</span><span class="sxs-lookup"><span data-stu-id="2edc2-171">In the Name field, type 'Name'.</span></span>
    * <span data-ttu-id="2edc2-172">Nome</span><span class="sxs-lookup"><span data-stu-id="2edc2-172">Name</span></span>  
37. <span data-ttu-id="2edc2-173">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2edc2-173">Click OK.</span></span>
38. <span data-ttu-id="2edc2-174">Fare clic su Aggiungi elemento.</span><span class="sxs-lookup"><span data-stu-id="2edc2-174">Click Add Element.</span></span>
39. <span data-ttu-id="2edc2-175">Nel campo Nome digitare "Banca".</span><span class="sxs-lookup"><span data-stu-id="2edc2-175">In the Name field, type 'Bank'.</span></span>
    * <span data-ttu-id="2edc2-176">Gestione banche</span><span class="sxs-lookup"><span data-stu-id="2edc2-176">Bank</span></span>  
40. <span data-ttu-id="2edc2-177">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2edc2-177">Click OK.</span></span>
41. <span data-ttu-id="2edc2-178">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Fornitore\Banca'.</span><span class="sxs-lookup"><span data-stu-id="2edc2-178">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank'.</span></span>
42. <span data-ttu-id="2edc2-179">Fare clic su Aggiungi elemento.</span><span class="sxs-lookup"><span data-stu-id="2edc2-179">Click Add Element.</span></span>
43. <span data-ttu-id="2edc2-180">Nel campo Nome digitare "RoutingNumber".</span><span class="sxs-lookup"><span data-stu-id="2edc2-180">In the Name field, type 'RoutingNumber'.</span></span>
    * <span data-ttu-id="2edc2-181">RoutingNumber</span><span class="sxs-lookup"><span data-stu-id="2edc2-181">RoutingNumber</span></span>  
44. <span data-ttu-id="2edc2-182">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2edc2-182">Click OK.</span></span>
45. <span data-ttu-id="2edc2-183">Fare clic su Aggiungi elemento.</span><span class="sxs-lookup"><span data-stu-id="2edc2-183">Click Add Element.</span></span>
46. <span data-ttu-id="2edc2-184">Nel campo Nome digitare "AccountNumber".</span><span class="sxs-lookup"><span data-stu-id="2edc2-184">In the Name field, type 'AccountNumber'.</span></span>
    * <span data-ttu-id="2edc2-185">AccountNumber</span><span class="sxs-lookup"><span data-stu-id="2edc2-185">AccountNumber</span></span>  
47. <span data-ttu-id="2edc2-186">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2edc2-186">Click OK.</span></span>
48. <span data-ttu-id="2edc2-187">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Fornitore'.</span><span class="sxs-lookup"><span data-stu-id="2edc2-187">In the tree, select 'Xml\Message\Payments\Item\Vendor'.</span></span>
49. <span data-ttu-id="2edc2-188">Fare clic su Copia.</span><span class="sxs-lookup"><span data-stu-id="2edc2-188">Click Copy.</span></span>
50. <span data-ttu-id="2edc2-189">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo'.</span><span class="sxs-lookup"><span data-stu-id="2edc2-189">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
51. <span data-ttu-id="2edc2-190">Fare clic su Incolla.</span><span class="sxs-lookup"><span data-stu-id="2edc2-190">Click Paste.</span></span>
52. <span data-ttu-id="2edc2-191">Nel campo Nome digitare "Pagante".</span><span class="sxs-lookup"><span data-stu-id="2edc2-191">In the Name field, type 'Payer'.</span></span>
    * <span data-ttu-id="2edc2-192">Pagante</span><span class="sxs-lookup"><span data-stu-id="2edc2-192">Payer</span></span>  
53. <span data-ttu-id="2edc2-193">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo'.</span><span class="sxs-lookup"><span data-stu-id="2edc2-193">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
54. <span data-ttu-id="2edc2-194">Fare clic su Aggiungi elemento.</span><span class="sxs-lookup"><span data-stu-id="2edc2-194">Click Add Element.</span></span>
55. <span data-ttu-id="2edc2-195">Nel campo Nome digitare "Valuta".</span><span class="sxs-lookup"><span data-stu-id="2edc2-195">In the Name field, type 'Currency'.</span></span>
    * <span data-ttu-id="2edc2-196">Valuta</span><span class="sxs-lookup"><span data-stu-id="2edc2-196">Currency</span></span>  
56. <span data-ttu-id="2edc2-197">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2edc2-197">Click OK.</span></span>
57. <span data-ttu-id="2edc2-198">Fare clic su Aggiungi elemento.</span><span class="sxs-lookup"><span data-stu-id="2edc2-198">Click Add Element.</span></span>
58. <span data-ttu-id="2edc2-199">Nel campo Nome digitare "Descrizione".</span><span class="sxs-lookup"><span data-stu-id="2edc2-199">In the Name field, type 'Description'.</span></span>
    * <span data-ttu-id="2edc2-200">descrizione</span><span class="sxs-lookup"><span data-stu-id="2edc2-200">Description</span></span>  
59. <span data-ttu-id="2edc2-201">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2edc2-201">Click OK.</span></span>
60. <span data-ttu-id="2edc2-202">Fare clic su Aggiungi elemento.</span><span class="sxs-lookup"><span data-stu-id="2edc2-202">Click Add Element.</span></span>
61. <span data-ttu-id="2edc2-203">Nel campo Nome digitare "TransDate".</span><span class="sxs-lookup"><span data-stu-id="2edc2-203">In the Name field, type 'TransDate'.</span></span>
    * <span data-ttu-id="2edc2-204">TransDate</span><span class="sxs-lookup"><span data-stu-id="2edc2-204">TransDate</span></span>  
62. <span data-ttu-id="2edc2-205">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2edc2-205">Click OK.</span></span>
63. <span data-ttu-id="2edc2-206">Fare clic su Aggiungi elemento.</span><span class="sxs-lookup"><span data-stu-id="2edc2-206">Click Add Element.</span></span>
64. <span data-ttu-id="2edc2-207">Nel campo Nome digitare "Importo".</span><span class="sxs-lookup"><span data-stu-id="2edc2-207">In the Name field, type 'Amount'.</span></span>
    * <span data-ttu-id="2edc2-208">Importo</span><span class="sxs-lookup"><span data-stu-id="2edc2-208">Amount</span></span>  
65. <span data-ttu-id="2edc2-209">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2edc2-209">Click OK.</span></span>

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a><span data-ttu-id="2edc2-210">Preparare i componenti del formato per eseguire il mapping a elementi del modello dati</span><span class="sxs-lookup"><span data-stu-id="2edc2-210">Prepare format components for mapping to data model elements</span></span>
1. <span data-ttu-id="2edc2-211">Nella struttura selezionare 'Xml\Messaggio\ProcessingDate'.</span><span class="sxs-lookup"><span data-stu-id="2edc2-211">In the tree, select 'Xml\Message\ProcessingDate'.</span></span>
2. <span data-ttu-id="2edc2-212">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="2edc2-212">Click Add to open the drop dialog.</span></span>
3. <span data-ttu-id="2edc2-213">Nella struttura selezionare 'Text\DateTime'.</span><span class="sxs-lookup"><span data-stu-id="2edc2-213">In the tree, select 'Text\DateTime'.</span></span>
4. <span data-ttu-id="2edc2-214">Nel campo Formato digitare "gg-MM-aaaa".</span><span class="sxs-lookup"><span data-stu-id="2edc2-214">In the Format field, type 'yyyy-MM-dd'.</span></span>
    * <span data-ttu-id="2edc2-215">yyyy-MM-dd</span><span class="sxs-lookup"><span data-stu-id="2edc2-215">yyyy-MM-dd</span></span>  
5. <span data-ttu-id="2edc2-216">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2edc2-216">Click OK.</span></span>
6. <span data-ttu-id="2edc2-217">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\TransDate'.</span><span class="sxs-lookup"><span data-stu-id="2edc2-217">In the tree, select 'Xml\Message\Payments\Item\TransDate'.</span></span>
7. <span data-ttu-id="2edc2-218">Fare clic su Aggiungi DateTime.</span><span class="sxs-lookup"><span data-stu-id="2edc2-218">Click Add DateTime.</span></span>
8. <span data-ttu-id="2edc2-219">Nel campo Formato digitare "gg-MM-aaaa".</span><span class="sxs-lookup"><span data-stu-id="2edc2-219">In the Format field, type 'yyyy-MM-dd'.</span></span>
    * <span data-ttu-id="2edc2-220">yyyy-MM-dd</span><span class="sxs-lookup"><span data-stu-id="2edc2-220">yyyy-MM-dd</span></span>  
9. <span data-ttu-id="2edc2-221">Nel campo Tipo di DateTime selezionare 'Date'.</span><span class="sxs-lookup"><span data-stu-id="2edc2-221">In the DateTime type field, select 'Date'.</span></span>
10. <span data-ttu-id="2edc2-222">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2edc2-222">Click OK.</span></span>
11. <span data-ttu-id="2edc2-223">Nella struttura selezionare 'Xml\Messaggio\MessageId'.</span><span class="sxs-lookup"><span data-stu-id="2edc2-223">In the tree, select 'Xml\Message\MessageId'.</span></span>
12. <span data-ttu-id="2edc2-224">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="2edc2-224">Click Add to open the drop dialog.</span></span>
13. <span data-ttu-id="2edc2-225">Nella struttura selezionare "Testo\Stringa".</span><span class="sxs-lookup"><span data-stu-id="2edc2-225">In the tree, select 'Text\String'.</span></span>
14. <span data-ttu-id="2edc2-226">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2edc2-226">Click OK.</span></span>
15. <span data-ttu-id="2edc2-227">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Fornitore\Nome'.</span><span class="sxs-lookup"><span data-stu-id="2edc2-227">In the tree, select 'Xml\Message\Payments\Item\Vendor\Name'.</span></span>
16. <span data-ttu-id="2edc2-228">Fare clic su Aggiungi stringa.</span><span class="sxs-lookup"><span data-stu-id="2edc2-228">Click Add String.</span></span>
17. <span data-ttu-id="2edc2-229">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2edc2-229">Click OK.</span></span>
18. <span data-ttu-id="2edc2-230">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Fornitore\Banca\RoutingNumber'.</span><span class="sxs-lookup"><span data-stu-id="2edc2-230">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber'.</span></span>
19. <span data-ttu-id="2edc2-231">Fare clic su Aggiungi stringa.</span><span class="sxs-lookup"><span data-stu-id="2edc2-231">Click Add String.</span></span>
20. <span data-ttu-id="2edc2-232">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2edc2-232">Click OK.</span></span>
21. <span data-ttu-id="2edc2-233">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Fornitore\Banca\AccountNumber'.</span><span class="sxs-lookup"><span data-stu-id="2edc2-233">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\AccountNumber'.</span></span>
22. <span data-ttu-id="2edc2-234">Fare clic su Aggiungi stringa.</span><span class="sxs-lookup"><span data-stu-id="2edc2-234">Click Add String.</span></span>
23. <span data-ttu-id="2edc2-235">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2edc2-235">Click OK.</span></span>
24. <span data-ttu-id="2edc2-236">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Pagante\Nome'.</span><span class="sxs-lookup"><span data-stu-id="2edc2-236">In the tree, select 'Xml\Message\Payments\Item\Payer\Name'.</span></span>
25. <span data-ttu-id="2edc2-237">Fare clic su Aggiungi stringa.</span><span class="sxs-lookup"><span data-stu-id="2edc2-237">Click Add String.</span></span>
26. <span data-ttu-id="2edc2-238">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2edc2-238">Click OK.</span></span>
27. <span data-ttu-id="2edc2-239">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Pagante\Banca\RoutingNumber'.</span><span class="sxs-lookup"><span data-stu-id="2edc2-239">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\RoutingNumber'.</span></span>
28. <span data-ttu-id="2edc2-240">Fare clic su Aggiungi stringa.</span><span class="sxs-lookup"><span data-stu-id="2edc2-240">Click Add String.</span></span>
29. <span data-ttu-id="2edc2-241">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2edc2-241">Click OK.</span></span>
30. <span data-ttu-id="2edc2-242">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Pagante\Banca\AccountNumber'.</span><span class="sxs-lookup"><span data-stu-id="2edc2-242">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\AccountNumber'.</span></span>
31. <span data-ttu-id="2edc2-243">Fare clic su Aggiungi stringa.</span><span class="sxs-lookup"><span data-stu-id="2edc2-243">Click Add String.</span></span>
32. <span data-ttu-id="2edc2-244">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2edc2-244">Click OK.</span></span>
33. <span data-ttu-id="2edc2-245">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Valuta'.</span><span class="sxs-lookup"><span data-stu-id="2edc2-245">In the tree, select 'Xml\Message\Payments\Item\Currency'.</span></span>
34. <span data-ttu-id="2edc2-246">Fare clic su Aggiungi stringa.</span><span class="sxs-lookup"><span data-stu-id="2edc2-246">Click Add String.</span></span>
35. <span data-ttu-id="2edc2-247">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2edc2-247">Click OK.</span></span>
36. <span data-ttu-id="2edc2-248">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Descrizione'.</span><span class="sxs-lookup"><span data-stu-id="2edc2-248">In the tree, select 'Xml\Message\Payments\Item\Description'.</span></span>
37. <span data-ttu-id="2edc2-249">Fare clic su Aggiungi stringa.</span><span class="sxs-lookup"><span data-stu-id="2edc2-249">Click Add String.</span></span>
38. <span data-ttu-id="2edc2-250">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2edc2-250">Click OK.</span></span>
39. <span data-ttu-id="2edc2-251">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Importo'.</span><span class="sxs-lookup"><span data-stu-id="2edc2-251">In the tree, select 'Xml\Message\Payments\Item\Amount'.</span></span>
40. <span data-ttu-id="2edc2-252">Fare clic su Aggiungi stringa.</span><span class="sxs-lookup"><span data-stu-id="2edc2-252">Click Add String.</span></span>
41. <span data-ttu-id="2edc2-253">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2edc2-253">Click OK.</span></span>
42. <span data-ttu-id="2edc2-254">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="2edc2-254">Click Save.</span></span>
43. <span data-ttu-id="2edc2-255">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2edc2-255">Close the page.</span></span>


