--- 
title: ER Creare una configurazione formato (novembre 2016)
description: "I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare una configurazione di formato per la creazione di report elettronici."
author: NickSelin
manager: AnnBe
ms.date: 11/27/2018
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
ms.sourcegitcommit: f004451a260b5be6c15c3975cd9e63ba9c1a7a2e
ms.openlocfilehash: 6fa5023a29c95ab9f10d8aacd51edc1a06c3c152
ms.contentlocale: it-it
ms.lasthandoff: 02/06/2019

---
# <a name="er-create-a-format-configuration-november-2016"></a><span data-ttu-id="d0679-103">ER Creare una configurazione formato (novembre 2016)</span><span class="sxs-lookup"><span data-stu-id="d0679-103">ER Create a format configuration (November 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d0679-104">I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare una configurazione di formato per la creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="d0679-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a format configuration for Electronic reporting (ER).</span></span> <span data-ttu-id="d0679-105">Tale configurazione di formato definirà il formato dei documenti elettronici utilizzati per l'elaborazione dei pagamenti.</span><span class="sxs-lookup"><span data-stu-id="d0679-105">This format configuration will define the format of electronic documents that are used for processing payments.</span></span> <span data-ttu-id="d0679-106">In questo esempio verrà creata una configurazione di formato per la società di esempio Litware, Inc. Per completare questi passaggi, è necessario aver completato prima i passaggi della procedura "Mappare il modello alle origini dati selezionate".</span><span class="sxs-lookup"><span data-stu-id="d0679-106">In this example, you will create a format configuration for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the “Map model to selected datasources” procedure.</span></span>


## <a name="create-a-new-format-configuration"></a><span data-ttu-id="d0679-107">Creare una nuova configurazione di formato</span><span class="sxs-lookup"><span data-stu-id="d0679-107">Create a new format configuration</span></span>
1. <span data-ttu-id="d0679-108">Andare ad **Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="d0679-108">Go to **Organization administration > Workspaces > Electronic reporting**.</span></span>
2. <span data-ttu-id="d0679-109">Fare clic su **Configurazioni report**.</span><span class="sxs-lookup"><span data-stu-id="d0679-109">Click **Reporting configurations**.</span></span>
3. <span data-ttu-id="d0679-110">Nella struttura selezionare **Pagamenti (modello semplificato)**.</span><span class="sxs-lookup"><span data-stu-id="d0679-110">In the tree, select **Payments (simplified model)**.</span></span>
4. <span data-ttu-id="d0679-111">Fare clic su **Crea configurazione** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="d0679-111">Click **Create configuration** to open the drop dialog.</span></span>

 > [!NOTE]
 > <span data-ttu-id="d0679-112">Se **Crea configurazione** non è visualizzato, necessario abilitare la modalità progettazione nella pagina **Parametri per la creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="d0679-112">If you don't see **Create configuration**, you must enable design mode on the **Electronic reporting parameters** page.</span></span> 
 
5. <span data-ttu-id="d0679-113">Nel campo **Nuovo** immettere **Formato in base al modello dati PaymentModel**.</span><span class="sxs-lookup"><span data-stu-id="d0679-113">In the **New** field, enter **Format based on data model PaymentModel**.</span></span>
6. <span data-ttu-id="d0679-114">Nel campo **Nome** digitare **BACS (fittizio per il Regno Unito)**.</span><span class="sxs-lookup"><span data-stu-id="d0679-114">In the **Name** field, type **BACS (UK fictitious)**.</span></span>
7. <span data-ttu-id="d0679-115">Nel campo **Descrizione** digitare **Formato di pagamento fornitore BACS (fittizio per il Regno Unito)**.</span><span class="sxs-lookup"><span data-stu-id="d0679-115">In the **Description** field, type **BACS vendor payment format (UK fictitious)**.</span></span>
    * <span data-ttu-id="d0679-116">Il provider di configurazione attiva viene inserito automaticamente in questo punto.</span><span class="sxs-lookup"><span data-stu-id="d0679-116">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="d0679-117">Tale provider potrà gestire la configurazione.</span><span class="sxs-lookup"><span data-stu-id="d0679-117">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="d0679-118">Altri provider possono utilizzare la configurazione, ma non potranno gestirla.</span><span class="sxs-lookup"><span data-stu-id="d0679-118">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
    * <span data-ttu-id="d0679-119">È possibile definire un formato specifico del documento elettronico.</span><span class="sxs-lookup"><span data-stu-id="d0679-119">A particular format of electronic document can be defined.</span></span> <span data-ttu-id="d0679-120">Lasciare vuoto il campo se si desidera selezionare un formato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d0679-120">Leave this field blank if you want to select a format at run-time.</span></span>  
8. <span data-ttu-id="d0679-121">Nel campo **Definizione modello dati** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d0679-121">In the **Data model definition** field, enter or select a value.</span></span>
9. <span data-ttu-id="d0679-122">Fare clic su **Crea configurazione**.</span><span class="sxs-lookup"><span data-stu-id="d0679-122">Click **Create configuration**.</span></span> <span data-ttu-id="d0679-123">È stata creata una nuova configurazione.</span><span class="sxs-lookup"><span data-stu-id="d0679-123">A new configuration has been created.</span></span> <span data-ttu-id="d0679-124">La versione bozza può essere utilizzata per archiviare il formato di progettazione per gestire i documenti elettronici.</span><span class="sxs-lookup"><span data-stu-id="d0679-124">The draft version can be used to store the design format for managing electronic documents.</span></span>  

 > [!NOTE]
 > <span data-ttu-id="d0679-125">Se **Crea configurazione** non è visualizzato, necessario abilitare la modalità progettazione nella pagina **Parametri per la creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="d0679-125">If you don't see **Create configuration**, you must enable design mode on the **Electronic reporting parameters** page.</span></span>


## <a name="design-the-format-of-an-electronic-document"></a><span data-ttu-id="d0679-126">Progettazione del formato di un documento elettronico</span><span class="sxs-lookup"><span data-stu-id="d0679-126">Design the format of an electronic document</span></span>
1. <span data-ttu-id="d0679-127">Fare clic su **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="d0679-127">Click **Designer**.</span></span>
2. <span data-ttu-id="d0679-128">Fare clic su **Aggiungi radice** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="d0679-128">Click **Add root** to open the drop dialog.</span></span>
3. <span data-ttu-id="d0679-129">Nella struttura selezionare **Comune\File**.</span><span class="sxs-lookup"><span data-stu-id="d0679-129">In the tree, select **Common\File**.</span></span>
4. <span data-ttu-id="d0679-130">Nel campo **Nome** digitare **XML**.</span><span class="sxs-lookup"><span data-stu-id="d0679-130">In the **Name** field, type **Xml**.</span></span>
5. <span data-ttu-id="d0679-131">Nel campo **Codifica** digitare **UTF-8**.</span><span class="sxs-lookup"><span data-stu-id="d0679-131">In the **Encoding** field, type **UTF-8**.</span></span>
6. <span data-ttu-id="d0679-132">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0679-132">Click **OK**.</span></span>
7. <span data-ttu-id="d0679-133">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="d0679-133">Click **Add**.</span></span>
8. <span data-ttu-id="d0679-134">Nella struttura selezionare **XML\Elemento**.</span><span class="sxs-lookup"><span data-stu-id="d0679-134">In the tree, select **XML\Element**.</span></span>
9. <span data-ttu-id="d0679-135">Nel campo **Nome** digitare **Messaggio**.</span><span class="sxs-lookup"><span data-stu-id="d0679-135">In the **Name** field, type **Message**.</span></span>
10. <span data-ttu-id="d0679-136">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0679-136">Click **OK**.</span></span>
11. <span data-ttu-id="d0679-137">Nella struttura selezionare **Xml\Messaggio**.</span><span class="sxs-lookup"><span data-stu-id="d0679-137">In the tree, select **Xml\Message**.</span></span>
12. <span data-ttu-id="d0679-138">Fare clic su **Aggiungi elemento**.</span><span class="sxs-lookup"><span data-stu-id="d0679-138">Click **Add Element**.</span></span>
13. <span data-ttu-id="d0679-139">Nel campo **Nome** digitare **ProcessingDate**.</span><span class="sxs-lookup"><span data-stu-id="d0679-139">In the **Name** field, type **ProcessingDate**.</span></span>
14. <span data-ttu-id="d0679-140">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0679-140">Click **OK**.</span></span>
15. <span data-ttu-id="d0679-141">Fare clic su **Aggiungi elemento**.</span><span class="sxs-lookup"><span data-stu-id="d0679-141">Click **Add Element**.</span></span>
16. <span data-ttu-id="d0679-142">Nel campo Nome digitare **MessageId**.</span><span class="sxs-lookup"><span data-stu-id="d0679-142">In the Name field, type **MessageId**.</span></span>
17. <span data-ttu-id="d0679-143">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0679-143">Click **OK**.</span></span>
18. <span data-ttu-id="d0679-144">Fare clic su **Aggiungi elemento**.</span><span class="sxs-lookup"><span data-stu-id="d0679-144">Click **Add Element**.</span></span>
19. <span data-ttu-id="d0679-145">Nel campo **Nome** digitare **Pagamenti**.</span><span class="sxs-lookup"><span data-stu-id="d0679-145">In the **Name** field, type **Payments**.</span></span>
20. <span data-ttu-id="d0679-146">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0679-146">Click **OK**.</span></span>
21. <span data-ttu-id="d0679-147">Nella struttura selezionare **Xml\Messaggio\Pagamenti**.</span><span class="sxs-lookup"><span data-stu-id="d0679-147">In the tree, select **Xml\Message\Payments**.</span></span>
22. <span data-ttu-id="d0679-148">Fare clic su **Aggiungi elemento**.</span><span class="sxs-lookup"><span data-stu-id="d0679-148">Click **Add Element**.</span></span>
23. <span data-ttu-id="d0679-149">Nel campo **Nome** digitare **Articolo**.</span><span class="sxs-lookup"><span data-stu-id="d0679-149">In the **Name** field, type **Item**.</span></span>
24. <span data-ttu-id="d0679-150">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0679-150">Click **OK**.</span></span>
25. <span data-ttu-id="d0679-151">Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo**.</span><span class="sxs-lookup"><span data-stu-id="d0679-151">In the tree, select **Xml\Message\Payments\Item**.</span></span>
26. <span data-ttu-id="d0679-152">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="d0679-152">Click **Add**.</span></span>
27. <span data-ttu-id="d0679-153">Nella struttura selezionare **XML\Attributo**.</span><span class="sxs-lookup"><span data-stu-id="d0679-153">In the tree, select **XML\Attribute**.</span></span>
28. <span data-ttu-id="d0679-154">Nel campo Nome digitare **ID**.</span><span class="sxs-lookup"><span data-stu-id="d0679-154">In the Name field, type **Id**.</span></span>
29. <span data-ttu-id="d0679-155">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0679-155">Click **OK**.</span></span>
30. <span data-ttu-id="d0679-156">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="d0679-156">Click **Add**.</span></span>
31. <span data-ttu-id="d0679-157">Nella struttura selezionare **XML\Elemento**.</span><span class="sxs-lookup"><span data-stu-id="d0679-157">In the tree, select **XML\Element**.</span></span>
32. <span data-ttu-id="d0679-158">Nel campo Nome digitare **Fornitore**.</span><span class="sxs-lookup"><span data-stu-id="d0679-158">In the Name field, type **Vendor**.</span></span>
33. <span data-ttu-id="d0679-159">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0679-159">Click **OK**.</span></span>
34. <span data-ttu-id="d0679-160">Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\Fornitore**.</span><span class="sxs-lookup"><span data-stu-id="d0679-160">In the tree, select **Xml\Message\Payments\Item\Vendor**.</span></span>
35. <span data-ttu-id="d0679-161">Fare clic su **Aggiungi elemento**.</span><span class="sxs-lookup"><span data-stu-id="d0679-161">Click **Add Element**.</span></span>
36. <span data-ttu-id="d0679-162">Nel campo Nome digitare **Nome**.</span><span class="sxs-lookup"><span data-stu-id="d0679-162">In the Name field, type **Name**.</span></span>
37. <span data-ttu-id="d0679-163">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0679-163">Click **OK**.</span></span>
38. <span data-ttu-id="d0679-164">Fare clic su **Aggiungi elemento**.</span><span class="sxs-lookup"><span data-stu-id="d0679-164">Click **Add Element**.</span></span>
39. <span data-ttu-id="d0679-165">Nel campo **Nome** digitare **Banca**.</span><span class="sxs-lookup"><span data-stu-id="d0679-165">In the **Name** field, type **Bank**.</span></span>
40. <span data-ttu-id="d0679-166">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0679-166">Click **OK**.</span></span>
41. <span data-ttu-id="d0679-167">Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\Fornitore\Banca**.</span><span class="sxs-lookup"><span data-stu-id="d0679-167">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank**.</span></span>
42. <span data-ttu-id="d0679-168">Fare clic su **Aggiungi elemento**.</span><span class="sxs-lookup"><span data-stu-id="d0679-168">Click **Add Element**.</span></span>
43. <span data-ttu-id="d0679-169">Nel campo **Nome** digitare **RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="d0679-169">In the **Name** field, type **RoutingNumber**.</span></span>
44. <span data-ttu-id="d0679-170">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0679-170">Click **OK**.</span></span>
45. <span data-ttu-id="d0679-171">Fare clic su **Aggiungi elemento**.</span><span class="sxs-lookup"><span data-stu-id="d0679-171">Click **Add Element**.</span></span>
46. <span data-ttu-id="d0679-172">Nel campo **Nome** digitare **AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="d0679-172">In the **Name** field, type **AccountNumber**.</span></span>
47. <span data-ttu-id="d0679-173">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0679-173">Click **OK**.</span></span>
48. <span data-ttu-id="d0679-174">Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\Fornitore**.</span><span class="sxs-lookup"><span data-stu-id="d0679-174">In the tree, select **Xml\Message\Payments\Item\Vendor**.</span></span>
49. <span data-ttu-id="d0679-175">Fare clic su **Copia**.</span><span class="sxs-lookup"><span data-stu-id="d0679-175">Click **Copy**.</span></span>
50. <span data-ttu-id="d0679-176">Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo**.</span><span class="sxs-lookup"><span data-stu-id="d0679-176">In the tree, select **Xml\Message\Payments\Item**.</span></span>
51. <span data-ttu-id="d0679-177">Fare clic su **Incolla**.</span><span class="sxs-lookup"><span data-stu-id="d0679-177">Click **Paste**.</span></span>
52. <span data-ttu-id="d0679-178">Nel campo **Nome** digitare **Pagante**.</span><span class="sxs-lookup"><span data-stu-id="d0679-178">In the **Name** field, type **Payer**.</span></span>
53. <span data-ttu-id="d0679-179">Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo**.</span><span class="sxs-lookup"><span data-stu-id="d0679-179">In the tree, select **Xml\Message\Payments\Item**.</span></span>
54. <span data-ttu-id="d0679-180">Fare clic su **Aggiungi elemento**.</span><span class="sxs-lookup"><span data-stu-id="d0679-180">Click **Add Element**.</span></span>
55. <span data-ttu-id="d0679-181">Nel campo **Nome** digitare **Valuta**.</span><span class="sxs-lookup"><span data-stu-id="d0679-181">In the **Name** field, type **Currency**.</span></span>
56. <span data-ttu-id="d0679-182">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0679-182">Click **OK**.</span></span>
57. <span data-ttu-id="d0679-183">Fare clic su **Aggiungi elemento**.</span><span class="sxs-lookup"><span data-stu-id="d0679-183">Click **Add Element**.</span></span>
58. <span data-ttu-id="d0679-184">Nel campo **Nome** digitare **Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="d0679-184">In the **Name** field, type **Description**.</span></span>
59. <span data-ttu-id="d0679-185">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0679-185">Click **OK**.</span></span>
60. <span data-ttu-id="d0679-186">Fare clic su **Aggiungi elemento**.</span><span class="sxs-lookup"><span data-stu-id="d0679-186">Click **Add Element**.</span></span>
61. <span data-ttu-id="d0679-187">Nel campo Nome digitare **TransDate**.</span><span class="sxs-lookup"><span data-stu-id="d0679-187">In the Name field, type **TransDate**.</span></span>
62. <span data-ttu-id="d0679-188">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0679-188">Click **OK**.</span></span>
63. <span data-ttu-id="d0679-189">Fare clic su **Aggiungi elemento**.</span><span class="sxs-lookup"><span data-stu-id="d0679-189">Click **Add Element**.</span></span>
64. <span data-ttu-id="d0679-190">Nel campo Nome digitare **Importo**.</span><span class="sxs-lookup"><span data-stu-id="d0679-190">In the Name field, type **Amount**.</span></span>
65. <span data-ttu-id="d0679-191">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0679-191">Click **OK**.</span></span>

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a><span data-ttu-id="d0679-192">Preparare i componenti del formato per eseguire il mapping a elementi del modello dati</span><span class="sxs-lookup"><span data-stu-id="d0679-192">Prepare format components for mapping to data model elements</span></span>
1. <span data-ttu-id="d0679-193">Nella struttura selezionare **Xml\Messaggio\ProcessingDate**.</span><span class="sxs-lookup"><span data-stu-id="d0679-193">In the tree, select **Xml\Message\ProcessingDate**.</span></span>
2. <span data-ttu-id="d0679-194">Fare clic su **Aggiungi** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="d0679-194">Click **Add** to open the drop dialog.</span></span>
3. <span data-ttu-id="d0679-195">Nella struttura selezionare **Text\DateTime**.</span><span class="sxs-lookup"><span data-stu-id="d0679-195">In the tree, select **Text\DateTime**.</span></span>
4. <span data-ttu-id="d0679-196">Nel campo **Formato** digitare **gg-MM-aaaa**.</span><span class="sxs-lookup"><span data-stu-id="d0679-196">In the **Format** field, type **yyyy-MM-dd**.</span></span>
5. <span data-ttu-id="d0679-197">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0679-197">Click **OK**.</span></span>
6. <span data-ttu-id="d0679-198">Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\TransDate**.</span><span class="sxs-lookup"><span data-stu-id="d0679-198">In the tree, select **Xml\Message\Payments\Item\TransDate**.</span></span>
7. <span data-ttu-id="d0679-199">Fare clic su **Aggiungi DateTime**.</span><span class="sxs-lookup"><span data-stu-id="d0679-199">Click **Add DateTime**.</span></span>
8. <span data-ttu-id="d0679-200">Nel campo **Formato** digitare **gg-MM-aaaa**.</span><span class="sxs-lookup"><span data-stu-id="d0679-200">In the **Format** field, type **yyyy-MM-dd**.</span></span>
9. <span data-ttu-id="d0679-201">Nel campo **DateTime** selezionare **Date**.</span><span class="sxs-lookup"><span data-stu-id="d0679-201">In the **DateTime** type field, select **Date**.</span></span>
10. <span data-ttu-id="d0679-202">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0679-202">Click **OK**.</span></span>
11. <span data-ttu-id="d0679-203">Nella struttura selezionare **Xml\Messaggio\MessageId**.</span><span class="sxs-lookup"><span data-stu-id="d0679-203">In the tree, select **Xml\Message\MessageId**.</span></span>
12. <span data-ttu-id="d0679-204">Fare clic su **Aggiungi** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="d0679-204">Click **Add** to open the drop dialog.</span></span>
13. <span data-ttu-id="d0679-205">Nella struttura selezionare **Testo\Stringa**.</span><span class="sxs-lookup"><span data-stu-id="d0679-205">In the tree, select **Text\String**.</span></span>
14. <span data-ttu-id="d0679-206">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0679-206">Click **OK**.</span></span>
15. <span data-ttu-id="d0679-207">Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\Fornitore\Nome**.</span><span class="sxs-lookup"><span data-stu-id="d0679-207">In the tree, select **Xml\Message\Payments\Item\Vendor\Name**.</span></span>
16. <span data-ttu-id="d0679-208">Fare clic su **Aggiungi stringa**.</span><span class="sxs-lookup"><span data-stu-id="d0679-208">Click **Add String**.</span></span>
17. <span data-ttu-id="d0679-209">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0679-209">Click **OK**.</span></span>
18. <span data-ttu-id="d0679-210">Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\Fornitore\Banca\RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="d0679-210">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber**.</span></span>
19. <span data-ttu-id="d0679-211">Fare clic su **Aggiungi stringa**.</span><span class="sxs-lookup"><span data-stu-id="d0679-211">Click **Add String**.</span></span>
20. <span data-ttu-id="d0679-212">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0679-212">Click **OK**.</span></span>
21. <span data-ttu-id="d0679-213">Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\Fornitore\Banca\AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="d0679-213">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank\AccountNumber**.</span></span>
22. <span data-ttu-id="d0679-214">Fare clic su **Aggiungi stringa**.</span><span class="sxs-lookup"><span data-stu-id="d0679-214">Click **Add String**.</span></span>
23. <span data-ttu-id="d0679-215">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0679-215">Click **OK**.</span></span>
24. <span data-ttu-id="d0679-216">Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\Pagante\Nome**.</span><span class="sxs-lookup"><span data-stu-id="d0679-216">In the tree, select **Xml\Message\Payments\Item\Payer\Name**.</span></span>
25. <span data-ttu-id="d0679-217">Fare clic su **Aggiungi stringa**.</span><span class="sxs-lookup"><span data-stu-id="d0679-217">Click **Add String**.</span></span>
26. <span data-ttu-id="d0679-218">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0679-218">Click **OK**.</span></span>
27. <span data-ttu-id="d0679-219">Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\Pagante\Banca\RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="d0679-219">In the tree, select **Xml\Message\Payments\Item\Payer\Bank\RoutingNumber**.</span></span>
28. <span data-ttu-id="d0679-220">Fare clic su **Aggiungi stringa**.</span><span class="sxs-lookup"><span data-stu-id="d0679-220">Click **Add String**.</span></span>
29. <span data-ttu-id="d0679-221">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0679-221">Click **OK**.</span></span>
30. <span data-ttu-id="d0679-222">Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\Pagante\Banca\AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="d0679-222">In the tree, select **Xml\Message\Payments\Item\Payer\Bank\AccountNumber**.</span></span>
31. <span data-ttu-id="d0679-223">Fare clic su **Aggiungi stringa**.</span><span class="sxs-lookup"><span data-stu-id="d0679-223">Click **Add String**.</span></span>
32. <span data-ttu-id="d0679-224">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0679-224">Click **OK**.</span></span>
33. <span data-ttu-id="d0679-225">Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\Valuta**.</span><span class="sxs-lookup"><span data-stu-id="d0679-225">In the tree, select **Xml\Message\Payments\Item\Currency**.</span></span>
34. <span data-ttu-id="d0679-226">Fare clic su **Aggiungi stringa**.</span><span class="sxs-lookup"><span data-stu-id="d0679-226">Click **Add String**.</span></span>
35. <span data-ttu-id="d0679-227">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0679-227">Click **OK**.</span></span>
36. <span data-ttu-id="d0679-228">Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="d0679-228">In the tree, select **Xml\Message\Payments\Item\Description**.</span></span>
37. <span data-ttu-id="d0679-229">Fare clic su **Aggiungi stringa**.</span><span class="sxs-lookup"><span data-stu-id="d0679-229">Click **Add String**.</span></span>
38. <span data-ttu-id="d0679-230">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0679-230">Click **OK**.</span></span>
39. <span data-ttu-id="d0679-231">Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\Importo**.</span><span class="sxs-lookup"><span data-stu-id="d0679-231">In the tree, select **Xml\Message\Payments\Item\Amount**.</span></span>
40. <span data-ttu-id="d0679-232">Fare clic su **Aggiungi stringa**.</span><span class="sxs-lookup"><span data-stu-id="d0679-232">Click **Add String**.</span></span>
41. <span data-ttu-id="d0679-233">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0679-233">Click **OK**.</span></span>
42. <span data-ttu-id="d0679-234">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d0679-234">Click **Save**.</span></span>
43. <span data-ttu-id="d0679-235">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d0679-235">Close the page.</span></span>


