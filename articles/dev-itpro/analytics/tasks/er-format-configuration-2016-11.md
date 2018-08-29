--- 
title: Creare configurazioni di formato per la creazione di report elettronici (ER)
description: "I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare una configurazione di formato per la creazione di report elettronici."
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
ms.openlocfilehash: 8c11f64fd899b8be4e6c3179913787eb2c32c6c6
ms.contentlocale: it-it
ms.lasthandoff: 08/09/2018

---
# <a name="create-electronic-reporting-er-format-configurations"></a><span data-ttu-id="f5d03-103">Creare configurazioni di formato per la creazione di report elettronici (ER)</span><span class="sxs-lookup"><span data-stu-id="f5d03-103">Create Electronic reporting (ER) format configurations</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f5d03-104">I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare una configurazione di formato per la creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="f5d03-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a format configuration for Electronic reporting (ER).</span></span> <span data-ttu-id="f5d03-105">Tale configurazione di formato definirà il formato dei documenti elettronici utilizzati per l'elaborazione dei pagamenti.</span><span class="sxs-lookup"><span data-stu-id="f5d03-105">This format configuration will define the format of electronic documents that are used for processing payments.</span></span> <span data-ttu-id="f5d03-106">In questo esempio verrà creata una configurazione di formato per la società di esempio Litware, Inc. Per completare questi passaggi, è necessario aver completato prima i passaggi della procedura "Mappare il modello alle origini dati selezionate".</span><span class="sxs-lookup"><span data-stu-id="f5d03-106">In this example, you will create a format configuration for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the “Map model to selected datasources” procedure.</span></span>


## <a name="create-a-new-format-configuration"></a><span data-ttu-id="f5d03-107">Creare una nuova configurazione di formato</span><span class="sxs-lookup"><span data-stu-id="f5d03-107">Create a new format configuration</span></span>
1. <span data-ttu-id="f5d03-108">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="f5d03-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="f5d03-109">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="f5d03-109">Click Reporting configurations.</span></span>
3. <span data-ttu-id="f5d03-110">Nella struttura selezionare "Pagamenti (modello semplificato)".</span><span class="sxs-lookup"><span data-stu-id="f5d03-110">In the tree, select 'Payments (simplified model)'.</span></span>
4. <span data-ttu-id="f5d03-111">Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .</span><span class="sxs-lookup"><span data-stu-id="f5d03-111">Click Create configuration to open the drop dialog.</span></span>
5. <span data-ttu-id="f5d03-112">Nel campo Nuovo immettere "Formato in base al modello dati PaymentModel".</span><span class="sxs-lookup"><span data-stu-id="f5d03-112">In the New field, enter 'Format based on data model PaymentModel'.</span></span>
6. <span data-ttu-id="f5d03-113">Nel campo Nome digitare "BACS (fittizio per il Regno Unito)".</span><span class="sxs-lookup"><span data-stu-id="f5d03-113">In the Name field, type 'BACS (UK fictitious)'.</span></span>
    * <span data-ttu-id="f5d03-114">BACS (fittizio per il Regno Unito)</span><span class="sxs-lookup"><span data-stu-id="f5d03-114">BACS (UK fictitious)</span></span>  
7. <span data-ttu-id="f5d03-115">Nel campo Descrizione digitare "Formato di pagamento fornitore BACS (fittizio per il Regno Unito)".</span><span class="sxs-lookup"><span data-stu-id="f5d03-115">In the Description field, type 'BACS vendor payment format (UK fictitious)'.</span></span>
    * <span data-ttu-id="f5d03-116">Formato di pagamento fornitore BACS (fittizio per il Regno Unito)</span><span class="sxs-lookup"><span data-stu-id="f5d03-116">BACS vendor payment format (UK fictitious)</span></span>  
    * <span data-ttu-id="f5d03-117">Il provider di configurazione attiva viene inserito automaticamente in questo punto.</span><span class="sxs-lookup"><span data-stu-id="f5d03-117">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="f5d03-118">Tale provider potrà gestire la configurazione.</span><span class="sxs-lookup"><span data-stu-id="f5d03-118">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="f5d03-119">Altri provider possono utilizzare la configurazione, ma non potranno gestirla.</span><span class="sxs-lookup"><span data-stu-id="f5d03-119">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
    * <span data-ttu-id="f5d03-120">È possibile definire un formato specifico del documento elettronico.</span><span class="sxs-lookup"><span data-stu-id="f5d03-120">A particular format of electronic document can be defined.</span></span> <span data-ttu-id="f5d03-121">Lasciare vuoto il campo se si desidera selezionare un formato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f5d03-121">Leave this field blank if you want to select a format at run-time.</span></span>  
8. <span data-ttu-id="f5d03-122">Nel campo Definizione modello dati immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="f5d03-122">In the Data model definition field, enter or select a value.</span></span>
9. <span data-ttu-id="f5d03-123">Fare clic su Crea configurazione.</span><span class="sxs-lookup"><span data-stu-id="f5d03-123">Click Create configuration.</span></span>
    * <span data-ttu-id="f5d03-124">È stata creata una nuova configurazione.</span><span class="sxs-lookup"><span data-stu-id="f5d03-124">A new configuration has been created.</span></span> <span data-ttu-id="f5d03-125">La versione bozza può essere utilizzata per archiviare il formato di progettazione per gestire i documenti elettronici.</span><span class="sxs-lookup"><span data-stu-id="f5d03-125">The draft version can be used to store the design format for managing electronic documents.</span></span>  

## <a name="design-format-of-electronic-document"></a><span data-ttu-id="f5d03-126">Formato di progettazione del documento elettronico</span><span class="sxs-lookup"><span data-stu-id="f5d03-126">Design format of electronic document</span></span>
1. <span data-ttu-id="f5d03-127">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="f5d03-127">Click Designer.</span></span>
2. <span data-ttu-id="f5d03-128">Fare clic su Aggiungi radice per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="f5d03-128">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="f5d03-129">Nella struttura selezionare "Comune\File".</span><span class="sxs-lookup"><span data-stu-id="f5d03-129">In the tree, select 'Common\File'.</span></span>
4. <span data-ttu-id="f5d03-130">Nel campo Nome digitare "XML".</span><span class="sxs-lookup"><span data-stu-id="f5d03-130">In the Name field, type 'Xml'.</span></span>
    * <span data-ttu-id="f5d03-131">XML</span><span class="sxs-lookup"><span data-stu-id="f5d03-131">Xml</span></span>  
5. <span data-ttu-id="f5d03-132">Nel campo Codifica digitare "UTF-8".</span><span class="sxs-lookup"><span data-stu-id="f5d03-132">In the Encoding field, type 'UTF-8'.</span></span>
    * <span data-ttu-id="f5d03-133">UTF-8</span><span class="sxs-lookup"><span data-stu-id="f5d03-133">UTF-8</span></span>  
6. <span data-ttu-id="f5d03-134">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5d03-134">Click OK.</span></span>
7. <span data-ttu-id="f5d03-135">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="f5d03-135">Click Add to open the drop dialog.</span></span>
8. <span data-ttu-id="f5d03-136">Nella struttura selezionare "XML\Elemento".</span><span class="sxs-lookup"><span data-stu-id="f5d03-136">In the tree, select 'XML\Element'.</span></span>
9. <span data-ttu-id="f5d03-137">Nel campo Nome digitare "Messaggio".</span><span class="sxs-lookup"><span data-stu-id="f5d03-137">In the Name field, type 'Message'.</span></span>
    * <span data-ttu-id="f5d03-138">Messaggio</span><span class="sxs-lookup"><span data-stu-id="f5d03-138">Message</span></span>  
10. <span data-ttu-id="f5d03-139">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5d03-139">Click OK.</span></span>
11. <span data-ttu-id="f5d03-140">Nella struttura selezionare 'Xml\Messaggio'.</span><span class="sxs-lookup"><span data-stu-id="f5d03-140">In the tree, select 'Xml\Message'.</span></span>
12. <span data-ttu-id="f5d03-141">Fare clic su Aggiungi elemento.</span><span class="sxs-lookup"><span data-stu-id="f5d03-141">Click Add Element.</span></span>
13. <span data-ttu-id="f5d03-142">Nel campo Nome digitare "ProcessingDate".</span><span class="sxs-lookup"><span data-stu-id="f5d03-142">In the Name field, type 'ProcessingDate'.</span></span>
    * <span data-ttu-id="f5d03-143">ProcessingDate</span><span class="sxs-lookup"><span data-stu-id="f5d03-143">ProcessingDate</span></span>  
14. <span data-ttu-id="f5d03-144">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5d03-144">Click OK.</span></span>
15. <span data-ttu-id="f5d03-145">Fare clic su Aggiungi elemento.</span><span class="sxs-lookup"><span data-stu-id="f5d03-145">Click Add Element.</span></span>
16. <span data-ttu-id="f5d03-146">Nel campo Nome digitare "MessageId".</span><span class="sxs-lookup"><span data-stu-id="f5d03-146">In the Name field, type 'MessageId'.</span></span>
    * <span data-ttu-id="f5d03-147">MessageId</span><span class="sxs-lookup"><span data-stu-id="f5d03-147">MessageId</span></span>  
17. <span data-ttu-id="f5d03-148">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5d03-148">Click OK.</span></span>
18. <span data-ttu-id="f5d03-149">Fare clic su Aggiungi elemento.</span><span class="sxs-lookup"><span data-stu-id="f5d03-149">Click Add Element.</span></span>
19. <span data-ttu-id="f5d03-150">Nel campo Nome digitare "Pagamenti".</span><span class="sxs-lookup"><span data-stu-id="f5d03-150">In the Name field, type 'Payments'.</span></span>
    * <span data-ttu-id="f5d03-151">Pagamenti</span><span class="sxs-lookup"><span data-stu-id="f5d03-151">Payments</span></span>  
20. <span data-ttu-id="f5d03-152">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5d03-152">Click OK.</span></span>
21. <span data-ttu-id="f5d03-153">Nella struttura selezionare 'Xml\Messaggio\Pagamenti'.</span><span class="sxs-lookup"><span data-stu-id="f5d03-153">In the tree, select 'Xml\Message\Payments'.</span></span>
22. <span data-ttu-id="f5d03-154">Fare clic su Aggiungi elemento.</span><span class="sxs-lookup"><span data-stu-id="f5d03-154">Click Add Element.</span></span>
23. <span data-ttu-id="f5d03-155">Nel campo Nome digitare "Articolo".</span><span class="sxs-lookup"><span data-stu-id="f5d03-155">In the Name field, type 'Item'.</span></span>
    * <span data-ttu-id="f5d03-156">Articolo</span><span class="sxs-lookup"><span data-stu-id="f5d03-156">Item</span></span>  
24. <span data-ttu-id="f5d03-157">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5d03-157">Click OK.</span></span>
25. <span data-ttu-id="f5d03-158">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo'.</span><span class="sxs-lookup"><span data-stu-id="f5d03-158">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
26. <span data-ttu-id="f5d03-159">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="f5d03-159">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="f5d03-160">Nella struttura selezionare "XML\Attributo".</span><span class="sxs-lookup"><span data-stu-id="f5d03-160">In the tree, select 'XML\Attribute'.</span></span>
28. <span data-ttu-id="f5d03-161">Nel campo Nome digitare "ID".</span><span class="sxs-lookup"><span data-stu-id="f5d03-161">In the Name field, type 'Id'.</span></span>
    * <span data-ttu-id="f5d03-162">ID</span><span class="sxs-lookup"><span data-stu-id="f5d03-162">Id</span></span>  
29. <span data-ttu-id="f5d03-163">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5d03-163">Click OK.</span></span>
30. <span data-ttu-id="f5d03-164">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="f5d03-164">Click Add to open the drop dialog.</span></span>
31. <span data-ttu-id="f5d03-165">Nella struttura selezionare "XML\Elemento".</span><span class="sxs-lookup"><span data-stu-id="f5d03-165">In the tree, select 'XML\Element'.</span></span>
32. <span data-ttu-id="f5d03-166">Nel campo Nome digitare "Fornitore".</span><span class="sxs-lookup"><span data-stu-id="f5d03-166">In the Name field, type 'Vendor'.</span></span>
    * <span data-ttu-id="f5d03-167">Fornitore</span><span class="sxs-lookup"><span data-stu-id="f5d03-167">Vendor</span></span>  
33. <span data-ttu-id="f5d03-168">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5d03-168">Click OK.</span></span>
34. <span data-ttu-id="f5d03-169">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Fornitore'.</span><span class="sxs-lookup"><span data-stu-id="f5d03-169">In the tree, select 'Xml\Message\Payments\Item\Vendor'.</span></span>
35. <span data-ttu-id="f5d03-170">Fare clic su Aggiungi elemento.</span><span class="sxs-lookup"><span data-stu-id="f5d03-170">Click Add Element.</span></span>
36. <span data-ttu-id="f5d03-171">Nel campo Nome digitare "Nome".</span><span class="sxs-lookup"><span data-stu-id="f5d03-171">In the Name field, type 'Name'.</span></span>
    * <span data-ttu-id="f5d03-172">Nome</span><span class="sxs-lookup"><span data-stu-id="f5d03-172">Name</span></span>  
37. <span data-ttu-id="f5d03-173">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5d03-173">Click OK.</span></span>
38. <span data-ttu-id="f5d03-174">Fare clic su Aggiungi elemento.</span><span class="sxs-lookup"><span data-stu-id="f5d03-174">Click Add Element.</span></span>
39. <span data-ttu-id="f5d03-175">Nel campo Nome digitare "Banca".</span><span class="sxs-lookup"><span data-stu-id="f5d03-175">In the Name field, type 'Bank'.</span></span>
    * <span data-ttu-id="f5d03-176">Gestione banche</span><span class="sxs-lookup"><span data-stu-id="f5d03-176">Bank</span></span>  
40. <span data-ttu-id="f5d03-177">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5d03-177">Click OK.</span></span>
41. <span data-ttu-id="f5d03-178">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Fornitore\Banca'.</span><span class="sxs-lookup"><span data-stu-id="f5d03-178">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank'.</span></span>
42. <span data-ttu-id="f5d03-179">Fare clic su Aggiungi elemento.</span><span class="sxs-lookup"><span data-stu-id="f5d03-179">Click Add Element.</span></span>
43. <span data-ttu-id="f5d03-180">Nel campo Nome digitare "RoutingNumber".</span><span class="sxs-lookup"><span data-stu-id="f5d03-180">In the Name field, type 'RoutingNumber'.</span></span>
    * <span data-ttu-id="f5d03-181">RoutingNumber</span><span class="sxs-lookup"><span data-stu-id="f5d03-181">RoutingNumber</span></span>  
44. <span data-ttu-id="f5d03-182">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5d03-182">Click OK.</span></span>
45. <span data-ttu-id="f5d03-183">Fare clic su Aggiungi elemento.</span><span class="sxs-lookup"><span data-stu-id="f5d03-183">Click Add Element.</span></span>
46. <span data-ttu-id="f5d03-184">Nel campo Nome digitare "AccountNumber".</span><span class="sxs-lookup"><span data-stu-id="f5d03-184">In the Name field, type 'AccountNumber'.</span></span>
    * <span data-ttu-id="f5d03-185">AccountNumber</span><span class="sxs-lookup"><span data-stu-id="f5d03-185">AccountNumber</span></span>  
47. <span data-ttu-id="f5d03-186">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5d03-186">Click OK.</span></span>
48. <span data-ttu-id="f5d03-187">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Fornitore'.</span><span class="sxs-lookup"><span data-stu-id="f5d03-187">In the tree, select 'Xml\Message\Payments\Item\Vendor'.</span></span>
49. <span data-ttu-id="f5d03-188">Fare clic su Copia.</span><span class="sxs-lookup"><span data-stu-id="f5d03-188">Click Copy.</span></span>
50. <span data-ttu-id="f5d03-189">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo'.</span><span class="sxs-lookup"><span data-stu-id="f5d03-189">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
51. <span data-ttu-id="f5d03-190">Fare clic su Incolla.</span><span class="sxs-lookup"><span data-stu-id="f5d03-190">Click Paste.</span></span>
52. <span data-ttu-id="f5d03-191">Nel campo Nome digitare "Pagante".</span><span class="sxs-lookup"><span data-stu-id="f5d03-191">In the Name field, type 'Payer'.</span></span>
    * <span data-ttu-id="f5d03-192">Pagante</span><span class="sxs-lookup"><span data-stu-id="f5d03-192">Payer</span></span>  
53. <span data-ttu-id="f5d03-193">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo'.</span><span class="sxs-lookup"><span data-stu-id="f5d03-193">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
54. <span data-ttu-id="f5d03-194">Fare clic su Aggiungi elemento.</span><span class="sxs-lookup"><span data-stu-id="f5d03-194">Click Add Element.</span></span>
55. <span data-ttu-id="f5d03-195">Nel campo Nome digitare "Valuta".</span><span class="sxs-lookup"><span data-stu-id="f5d03-195">In the Name field, type 'Currency'.</span></span>
    * <span data-ttu-id="f5d03-196">Valuta</span><span class="sxs-lookup"><span data-stu-id="f5d03-196">Currency</span></span>  
56. <span data-ttu-id="f5d03-197">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5d03-197">Click OK.</span></span>
57. <span data-ttu-id="f5d03-198">Fare clic su Aggiungi elemento.</span><span class="sxs-lookup"><span data-stu-id="f5d03-198">Click Add Element.</span></span>
58. <span data-ttu-id="f5d03-199">Nel campo Nome digitare "Descrizione".</span><span class="sxs-lookup"><span data-stu-id="f5d03-199">In the Name field, type 'Description'.</span></span>
    * <span data-ttu-id="f5d03-200">descrizione</span><span class="sxs-lookup"><span data-stu-id="f5d03-200">Description</span></span>  
59. <span data-ttu-id="f5d03-201">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5d03-201">Click OK.</span></span>
60. <span data-ttu-id="f5d03-202">Fare clic su Aggiungi elemento.</span><span class="sxs-lookup"><span data-stu-id="f5d03-202">Click Add Element.</span></span>
61. <span data-ttu-id="f5d03-203">Nel campo Nome digitare "TransDate".</span><span class="sxs-lookup"><span data-stu-id="f5d03-203">In the Name field, type 'TransDate'.</span></span>
    * <span data-ttu-id="f5d03-204">TransDate</span><span class="sxs-lookup"><span data-stu-id="f5d03-204">TransDate</span></span>  
62. <span data-ttu-id="f5d03-205">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5d03-205">Click OK.</span></span>
63. <span data-ttu-id="f5d03-206">Fare clic su Aggiungi elemento.</span><span class="sxs-lookup"><span data-stu-id="f5d03-206">Click Add Element.</span></span>
64. <span data-ttu-id="f5d03-207">Nel campo Nome digitare "Importo".</span><span class="sxs-lookup"><span data-stu-id="f5d03-207">In the Name field, type 'Amount'.</span></span>
    * <span data-ttu-id="f5d03-208">Importo</span><span class="sxs-lookup"><span data-stu-id="f5d03-208">Amount</span></span>  
65. <span data-ttu-id="f5d03-209">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5d03-209">Click OK.</span></span>

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a><span data-ttu-id="f5d03-210">Preparare i componenti del formato per eseguire il mapping a elementi del modello dati</span><span class="sxs-lookup"><span data-stu-id="f5d03-210">Prepare format components for mapping to data model elements</span></span>
1. <span data-ttu-id="f5d03-211">Nella struttura selezionare 'Xml\Messaggio\ProcessingDate'.</span><span class="sxs-lookup"><span data-stu-id="f5d03-211">In the tree, select 'Xml\Message\ProcessingDate'.</span></span>
2. <span data-ttu-id="f5d03-212">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="f5d03-212">Click Add to open the drop dialog.</span></span>
3. <span data-ttu-id="f5d03-213">Nella struttura selezionare 'Text\DateTime'.</span><span class="sxs-lookup"><span data-stu-id="f5d03-213">In the tree, select 'Text\DateTime'.</span></span>
4. <span data-ttu-id="f5d03-214">Nel campo Formato digitare "gg-MM-aaaa".</span><span class="sxs-lookup"><span data-stu-id="f5d03-214">In the Format field, type 'yyyy-MM-dd'.</span></span>
    * <span data-ttu-id="f5d03-215">yyyy-MM-dd</span><span class="sxs-lookup"><span data-stu-id="f5d03-215">yyyy-MM-dd</span></span>  
5. <span data-ttu-id="f5d03-216">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5d03-216">Click OK.</span></span>
6. <span data-ttu-id="f5d03-217">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\TransDate'.</span><span class="sxs-lookup"><span data-stu-id="f5d03-217">In the tree, select 'Xml\Message\Payments\Item\TransDate'.</span></span>
7. <span data-ttu-id="f5d03-218">Fare clic su Aggiungi DateTime.</span><span class="sxs-lookup"><span data-stu-id="f5d03-218">Click Add DateTime.</span></span>
8. <span data-ttu-id="f5d03-219">Nel campo Formato digitare "gg-MM-aaaa".</span><span class="sxs-lookup"><span data-stu-id="f5d03-219">In the Format field, type 'yyyy-MM-dd'.</span></span>
    * <span data-ttu-id="f5d03-220">yyyy-MM-dd</span><span class="sxs-lookup"><span data-stu-id="f5d03-220">yyyy-MM-dd</span></span>  
9. <span data-ttu-id="f5d03-221">Nel campo Tipo di DateTime selezionare 'Date'.</span><span class="sxs-lookup"><span data-stu-id="f5d03-221">In the DateTime type field, select 'Date'.</span></span>
10. <span data-ttu-id="f5d03-222">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5d03-222">Click OK.</span></span>
11. <span data-ttu-id="f5d03-223">Nella struttura selezionare 'Xml\Messaggio\MessageId'.</span><span class="sxs-lookup"><span data-stu-id="f5d03-223">In the tree, select 'Xml\Message\MessageId'.</span></span>
12. <span data-ttu-id="f5d03-224">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="f5d03-224">Click Add to open the drop dialog.</span></span>
13. <span data-ttu-id="f5d03-225">Nella struttura selezionare "Testo\Stringa".</span><span class="sxs-lookup"><span data-stu-id="f5d03-225">In the tree, select 'Text\String'.</span></span>
14. <span data-ttu-id="f5d03-226">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5d03-226">Click OK.</span></span>
15. <span data-ttu-id="f5d03-227">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Fornitore\Nome'.</span><span class="sxs-lookup"><span data-stu-id="f5d03-227">In the tree, select 'Xml\Message\Payments\Item\Vendor\Name'.</span></span>
16. <span data-ttu-id="f5d03-228">Fare clic su Aggiungi stringa.</span><span class="sxs-lookup"><span data-stu-id="f5d03-228">Click Add String.</span></span>
17. <span data-ttu-id="f5d03-229">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5d03-229">Click OK.</span></span>
18. <span data-ttu-id="f5d03-230">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Fornitore\Banca\RoutingNumber'.</span><span class="sxs-lookup"><span data-stu-id="f5d03-230">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber'.</span></span>
19. <span data-ttu-id="f5d03-231">Fare clic su Aggiungi stringa.</span><span class="sxs-lookup"><span data-stu-id="f5d03-231">Click Add String.</span></span>
20. <span data-ttu-id="f5d03-232">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5d03-232">Click OK.</span></span>
21. <span data-ttu-id="f5d03-233">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Fornitore\Banca\AccountNumber'.</span><span class="sxs-lookup"><span data-stu-id="f5d03-233">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\AccountNumber'.</span></span>
22. <span data-ttu-id="f5d03-234">Fare clic su Aggiungi stringa.</span><span class="sxs-lookup"><span data-stu-id="f5d03-234">Click Add String.</span></span>
23. <span data-ttu-id="f5d03-235">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5d03-235">Click OK.</span></span>
24. <span data-ttu-id="f5d03-236">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Pagante\Nome'.</span><span class="sxs-lookup"><span data-stu-id="f5d03-236">In the tree, select 'Xml\Message\Payments\Item\Payer\Name'.</span></span>
25. <span data-ttu-id="f5d03-237">Fare clic su Aggiungi stringa.</span><span class="sxs-lookup"><span data-stu-id="f5d03-237">Click Add String.</span></span>
26. <span data-ttu-id="f5d03-238">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5d03-238">Click OK.</span></span>
27. <span data-ttu-id="f5d03-239">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Pagante\Banca\RoutingNumber'.</span><span class="sxs-lookup"><span data-stu-id="f5d03-239">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\RoutingNumber'.</span></span>
28. <span data-ttu-id="f5d03-240">Fare clic su Aggiungi stringa.</span><span class="sxs-lookup"><span data-stu-id="f5d03-240">Click Add String.</span></span>
29. <span data-ttu-id="f5d03-241">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5d03-241">Click OK.</span></span>
30. <span data-ttu-id="f5d03-242">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Pagante\Banca\AccountNumber'.</span><span class="sxs-lookup"><span data-stu-id="f5d03-242">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\AccountNumber'.</span></span>
31. <span data-ttu-id="f5d03-243">Fare clic su Aggiungi stringa.</span><span class="sxs-lookup"><span data-stu-id="f5d03-243">Click Add String.</span></span>
32. <span data-ttu-id="f5d03-244">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5d03-244">Click OK.</span></span>
33. <span data-ttu-id="f5d03-245">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Valuta'.</span><span class="sxs-lookup"><span data-stu-id="f5d03-245">In the tree, select 'Xml\Message\Payments\Item\Currency'.</span></span>
34. <span data-ttu-id="f5d03-246">Fare clic su Aggiungi stringa.</span><span class="sxs-lookup"><span data-stu-id="f5d03-246">Click Add String.</span></span>
35. <span data-ttu-id="f5d03-247">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5d03-247">Click OK.</span></span>
36. <span data-ttu-id="f5d03-248">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Descrizione'.</span><span class="sxs-lookup"><span data-stu-id="f5d03-248">In the tree, select 'Xml\Message\Payments\Item\Description'.</span></span>
37. <span data-ttu-id="f5d03-249">Fare clic su Aggiungi stringa.</span><span class="sxs-lookup"><span data-stu-id="f5d03-249">Click Add String.</span></span>
38. <span data-ttu-id="f5d03-250">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5d03-250">Click OK.</span></span>
39. <span data-ttu-id="f5d03-251">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Importo'.</span><span class="sxs-lookup"><span data-stu-id="f5d03-251">In the tree, select 'Xml\Message\Payments\Item\Amount'.</span></span>
40. <span data-ttu-id="f5d03-252">Fare clic su Aggiungi stringa.</span><span class="sxs-lookup"><span data-stu-id="f5d03-252">Click Add String.</span></span>
41. <span data-ttu-id="f5d03-253">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5d03-253">Click OK.</span></span>
42. <span data-ttu-id="f5d03-254">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="f5d03-254">Click Save.</span></span>
43. <span data-ttu-id="f5d03-255">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="f5d03-255">Close the page.</span></span>


