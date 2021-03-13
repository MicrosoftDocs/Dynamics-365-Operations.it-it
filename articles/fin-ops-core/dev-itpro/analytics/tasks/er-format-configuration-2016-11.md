---
title: ER Creare una configurazione formato (novembre 2016)
description: In questo argomento viene illustrato come creare una configurazione di formato per la creazione di report elettronici (ER).
author: NickSelin
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9404d1e242c83d2103d1f24c42589c33b9f57f02
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092252"
---
# <a name="er-create-a-format-configuration-november-2016"></a><span data-ttu-id="010c0-103">ER Creare una configurazione formato (novembre 2016)</span><span class="sxs-lookup"><span data-stu-id="010c0-103">ER Create a format configuration (November 2016)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="010c0-104">Questo argomento illustra come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare una configurazione di formato per la creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="010c0-104">This topic explains how a user in the System Administrator or Electronic Reporting Developer role can create a format configuration for Electronic reporting (ER).</span></span> <span data-ttu-id="010c0-105">Tale configurazione di formato definirà il formato dei documenti elettronici utilizzati per l'elaborazione dei pagamenti.</span><span class="sxs-lookup"><span data-stu-id="010c0-105">This format configuration will define the format of electronic documents that are used for processing payments.</span></span> <span data-ttu-id="010c0-106">In questo esempio verrà creata una configurazione di formato per la società di esempio Litware, Inc. Per completare questi passaggi, è necessario aver completato prima i passaggi della procedura "Mappare il modello alle origini dati selezionate".</span><span class="sxs-lookup"><span data-stu-id="010c0-106">In this example, you will create a format configuration for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the "Map model to selected datasources" procedure.</span></span>


## <a name="create-a-new-format-configuration"></a><span data-ttu-id="010c0-107">Creare una nuova configurazione di formato</span><span class="sxs-lookup"><span data-stu-id="010c0-107">Create a new format configuration</span></span>
1. <span data-ttu-id="010c0-108">Andare ad **Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="010c0-108">Go to **Organization administration > Workspaces > Electronic reporting**.</span></span>
2. <span data-ttu-id="010c0-109">Fare clic su **Configurazioni report**.</span><span class="sxs-lookup"><span data-stu-id="010c0-109">Click **Reporting configurations**.</span></span>
3. <span data-ttu-id="010c0-110">Nella struttura selezionare **Pagamenti (modello semplificato)**.</span><span class="sxs-lookup"><span data-stu-id="010c0-110">In the tree, select **Payments (simplified model)**.</span></span>
4. <span data-ttu-id="010c0-111">Fare clic su **Crea configurazione** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="010c0-111">Click **Create configuration** to open the drop dialog.</span></span>

 > [!NOTE]
 > <span data-ttu-id="010c0-112">Se **Crea configurazione** non è visualizzato, necessario abilitare la modalità progettazione nella pagina **Parametri per la creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="010c0-112">If you don't see **Create configuration**, you must enable design mode on the **Electronic reporting parameters** page.</span></span> 
 
5. <span data-ttu-id="010c0-113">Nel campo **Nuovo** immettere **Formato in base al modello dati PaymentModel**.</span><span class="sxs-lookup"><span data-stu-id="010c0-113">In the **New** field, enter **Format based on data model PaymentModel**.</span></span>
6. <span data-ttu-id="010c0-114">Nel campo **Nome** digitare **BACS (fittizio per il Regno Unito)**.</span><span class="sxs-lookup"><span data-stu-id="010c0-114">In the **Name** field, type **BACS (UK fictitious)**.</span></span>
7. <span data-ttu-id="010c0-115">Nel campo **Descrizione** digitare **Formato di pagamento fornitore BACS (fittizio per il Regno Unito)**.</span><span class="sxs-lookup"><span data-stu-id="010c0-115">In the **Description** field, type **BACS vendor payment format (UK fictitious)**.</span></span>
    * <span data-ttu-id="010c0-116">Il provider di configurazione attiva viene inserito automaticamente in questo punto.</span><span class="sxs-lookup"><span data-stu-id="010c0-116">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="010c0-117">Tale provider potrà gestire la configurazione.</span><span class="sxs-lookup"><span data-stu-id="010c0-117">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="010c0-118">Altri provider possono utilizzare la configurazione, ma non potranno gestirla.</span><span class="sxs-lookup"><span data-stu-id="010c0-118">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
    * <span data-ttu-id="010c0-119">È possibile definire un formato specifico del documento elettronico.</span><span class="sxs-lookup"><span data-stu-id="010c0-119">A particular format of electronic document can be defined.</span></span> <span data-ttu-id="010c0-120">Lasciare vuoto il campo se si desidera selezionare un formato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="010c0-120">Leave this field blank if you want to select a format at run-time.</span></span>  
8. <span data-ttu-id="010c0-121">Nel campo **Definizione modello dati** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="010c0-121">In the **Data model definition** field, enter or select a value.</span></span>
9. <span data-ttu-id="010c0-122">Fare clic su **Crea configurazione**.</span><span class="sxs-lookup"><span data-stu-id="010c0-122">Click **Create configuration**.</span></span> <span data-ttu-id="010c0-123">È stata creata una nuova configurazione.</span><span class="sxs-lookup"><span data-stu-id="010c0-123">A new configuration has been created.</span></span> <span data-ttu-id="010c0-124">La versione bozza può essere utilizzata per archiviare il formato di progettazione per gestire i documenti elettronici.</span><span class="sxs-lookup"><span data-stu-id="010c0-124">The draft version can be used to store the design format for managing electronic documents.</span></span>  

## <a name="design-the-format-of-an-electronic-document"></a><span data-ttu-id="010c0-125">Progettazione del formato di un documento elettronico</span><span class="sxs-lookup"><span data-stu-id="010c0-125">Design the format of an electronic document</span></span>
1. <span data-ttu-id="010c0-126">Fare clic su **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="010c0-126">Click **Designer**.</span></span>
2. <span data-ttu-id="010c0-127">Fare clic su **Aggiungi radice** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="010c0-127">Click **Add root** to open the drop dialog.</span></span>
3. <span data-ttu-id="010c0-128">Nella struttura selezionare **Comune\File**.</span><span class="sxs-lookup"><span data-stu-id="010c0-128">In the tree, select **Common\File**.</span></span>
4. <span data-ttu-id="010c0-129">Nel campo **Nome** digitare **XML**.</span><span class="sxs-lookup"><span data-stu-id="010c0-129">In the **Name** field, type **Xml**.</span></span>
5. <span data-ttu-id="010c0-130">Nel campo **Codifica** digitare **UTF-8**.</span><span class="sxs-lookup"><span data-stu-id="010c0-130">In the **Encoding** field, type **UTF-8**.</span></span>
6. <span data-ttu-id="010c0-131">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="010c0-131">Click **OK**.</span></span>
7. <span data-ttu-id="010c0-132">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="010c0-132">Click **Add**.</span></span>
8. <span data-ttu-id="010c0-133">Nella struttura selezionare **XML\Elemento**.</span><span class="sxs-lookup"><span data-stu-id="010c0-133">In the tree, select **XML\Element**.</span></span>
9. <span data-ttu-id="010c0-134">Nel campo **Nome** digitare **Messaggio**.</span><span class="sxs-lookup"><span data-stu-id="010c0-134">In the **Name** field, type **Message**.</span></span>
10. <span data-ttu-id="010c0-135">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="010c0-135">Click **OK**.</span></span>
11. <span data-ttu-id="010c0-136">Nella struttura selezionare **Xml\Messaggio**.</span><span class="sxs-lookup"><span data-stu-id="010c0-136">In the tree, select **Xml\Message**.</span></span>
12. <span data-ttu-id="010c0-137">Fare clic su **Aggiungi elemento**.</span><span class="sxs-lookup"><span data-stu-id="010c0-137">Click **Add Element**.</span></span>
13. <span data-ttu-id="010c0-138">Nel campo **Nome** digitare **ProcessingDate**.</span><span class="sxs-lookup"><span data-stu-id="010c0-138">In the **Name** field, type **ProcessingDate**.</span></span>
14. <span data-ttu-id="010c0-139">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="010c0-139">Click **OK**.</span></span>
15. <span data-ttu-id="010c0-140">Fare clic su **Aggiungi elemento**.</span><span class="sxs-lookup"><span data-stu-id="010c0-140">Click **Add Element**.</span></span>
16. <span data-ttu-id="010c0-141">Nel campo Nome digitare **MessageId**.</span><span class="sxs-lookup"><span data-stu-id="010c0-141">In the Name field, type **MessageId**.</span></span>
17. <span data-ttu-id="010c0-142">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="010c0-142">Click **OK**.</span></span>
18. <span data-ttu-id="010c0-143">Fare clic su **Aggiungi elemento**.</span><span class="sxs-lookup"><span data-stu-id="010c0-143">Click **Add Element**.</span></span>
19. <span data-ttu-id="010c0-144">Nel campo **Nome** digitare **Pagamenti**.</span><span class="sxs-lookup"><span data-stu-id="010c0-144">In the **Name** field, type **Payments**.</span></span>
20. <span data-ttu-id="010c0-145">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="010c0-145">Click **OK**.</span></span>
21. <span data-ttu-id="010c0-146">Nella struttura selezionare **Xml\Messaggio\Pagamenti**.</span><span class="sxs-lookup"><span data-stu-id="010c0-146">In the tree, select **Xml\Message\Payments**.</span></span>
22. <span data-ttu-id="010c0-147">Fare clic su **Aggiungi elemento**.</span><span class="sxs-lookup"><span data-stu-id="010c0-147">Click **Add Element**.</span></span>
23. <span data-ttu-id="010c0-148">Nel campo **Nome** digitare **Articolo**.</span><span class="sxs-lookup"><span data-stu-id="010c0-148">In the **Name** field, type **Item**.</span></span>
24. <span data-ttu-id="010c0-149">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="010c0-149">Click **OK**.</span></span>
25. <span data-ttu-id="010c0-150">Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo**.</span><span class="sxs-lookup"><span data-stu-id="010c0-150">In the tree, select **Xml\Message\Payments\Item**.</span></span>
26. <span data-ttu-id="010c0-151">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="010c0-151">Click **Add**.</span></span>
27. <span data-ttu-id="010c0-152">Nella struttura selezionare **XML\Attributo**.</span><span class="sxs-lookup"><span data-stu-id="010c0-152">In the tree, select **XML\Attribute**.</span></span>
28. <span data-ttu-id="010c0-153">Nel campo Nome digitare **ID**.</span><span class="sxs-lookup"><span data-stu-id="010c0-153">In the Name field, type **Id**.</span></span>
29. <span data-ttu-id="010c0-154">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="010c0-154">Click **OK**.</span></span>
30. <span data-ttu-id="010c0-155">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="010c0-155">Click **Add**.</span></span>
31. <span data-ttu-id="010c0-156">Nella struttura selezionare **XML\Elemento**.</span><span class="sxs-lookup"><span data-stu-id="010c0-156">In the tree, select **XML\Element**.</span></span>
32. <span data-ttu-id="010c0-157">Nel campo Nome digitare **Fornitore**.</span><span class="sxs-lookup"><span data-stu-id="010c0-157">In the Name field, type **Vendor**.</span></span>
33. <span data-ttu-id="010c0-158">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="010c0-158">Click **OK**.</span></span>
34. <span data-ttu-id="010c0-159">Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\Fornitore**.</span><span class="sxs-lookup"><span data-stu-id="010c0-159">In the tree, select **Xml\Message\Payments\Item\Vendor**.</span></span>
35. <span data-ttu-id="010c0-160">Fare clic su **Aggiungi elemento**.</span><span class="sxs-lookup"><span data-stu-id="010c0-160">Click **Add Element**.</span></span>
36. <span data-ttu-id="010c0-161">Nel campo Nome digitare **Nome**.</span><span class="sxs-lookup"><span data-stu-id="010c0-161">In the Name field, type **Name**.</span></span>
37. <span data-ttu-id="010c0-162">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="010c0-162">Click **OK**.</span></span>
38. <span data-ttu-id="010c0-163">Fare clic su **Aggiungi elemento**.</span><span class="sxs-lookup"><span data-stu-id="010c0-163">Click **Add Element**.</span></span>
39. <span data-ttu-id="010c0-164">Nel campo **Nome** digitare **Banca**.</span><span class="sxs-lookup"><span data-stu-id="010c0-164">In the **Name** field, type **Bank**.</span></span>
40. <span data-ttu-id="010c0-165">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="010c0-165">Click **OK**.</span></span>
41. <span data-ttu-id="010c0-166">Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\Fornitore\Banca**.</span><span class="sxs-lookup"><span data-stu-id="010c0-166">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank**.</span></span>
42. <span data-ttu-id="010c0-167">Fare clic su **Aggiungi elemento**.</span><span class="sxs-lookup"><span data-stu-id="010c0-167">Click **Add Element**.</span></span>
43. <span data-ttu-id="010c0-168">Nel campo **Nome** digitare **RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="010c0-168">In the **Name** field, type **RoutingNumber**.</span></span>
44. <span data-ttu-id="010c0-169">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="010c0-169">Click **OK**.</span></span>
45. <span data-ttu-id="010c0-170">Fare clic su **Aggiungi elemento**.</span><span class="sxs-lookup"><span data-stu-id="010c0-170">Click **Add Element**.</span></span>
46. <span data-ttu-id="010c0-171">Nel campo **Nome** digitare **AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="010c0-171">In the **Name** field, type **AccountNumber**.</span></span>
47. <span data-ttu-id="010c0-172">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="010c0-172">Click **OK**.</span></span>
48. <span data-ttu-id="010c0-173">Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\Fornitore**.</span><span class="sxs-lookup"><span data-stu-id="010c0-173">In the tree, select **Xml\Message\Payments\Item\Vendor**.</span></span>
49. <span data-ttu-id="010c0-174">Fare clic su **Copia**.</span><span class="sxs-lookup"><span data-stu-id="010c0-174">Click **Copy**.</span></span>
50. <span data-ttu-id="010c0-175">Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo**.</span><span class="sxs-lookup"><span data-stu-id="010c0-175">In the tree, select **Xml\Message\Payments\Item**.</span></span>
51. <span data-ttu-id="010c0-176">Fare clic su **Incolla**.</span><span class="sxs-lookup"><span data-stu-id="010c0-176">Click **Paste**.</span></span>
52. <span data-ttu-id="010c0-177">Nel campo **Nome** digitare **Pagante**.</span><span class="sxs-lookup"><span data-stu-id="010c0-177">In the **Name** field, type **Payer**.</span></span>
53. <span data-ttu-id="010c0-178">Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo**.</span><span class="sxs-lookup"><span data-stu-id="010c0-178">In the tree, select **Xml\Message\Payments\Item**.</span></span>
54. <span data-ttu-id="010c0-179">Fare clic su **Aggiungi elemento**.</span><span class="sxs-lookup"><span data-stu-id="010c0-179">Click **Add Element**.</span></span>
55. <span data-ttu-id="010c0-180">Nel campo **Nome** digitare **Valuta**.</span><span class="sxs-lookup"><span data-stu-id="010c0-180">In the **Name** field, type **Currency**.</span></span>
56. <span data-ttu-id="010c0-181">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="010c0-181">Click **OK**.</span></span>
57. <span data-ttu-id="010c0-182">Fare clic su **Aggiungi elemento**.</span><span class="sxs-lookup"><span data-stu-id="010c0-182">Click **Add Element**.</span></span>
58. <span data-ttu-id="010c0-183">Nel campo **Nome** digitare **Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="010c0-183">In the **Name** field, type **Description**.</span></span>
59. <span data-ttu-id="010c0-184">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="010c0-184">Click **OK**.</span></span>
60. <span data-ttu-id="010c0-185">Fare clic su **Aggiungi elemento**.</span><span class="sxs-lookup"><span data-stu-id="010c0-185">Click **Add Element**.</span></span>
61. <span data-ttu-id="010c0-186">Nel campo Nome digitare **TransDate**.</span><span class="sxs-lookup"><span data-stu-id="010c0-186">In the Name field, type **TransDate**.</span></span>
62. <span data-ttu-id="010c0-187">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="010c0-187">Click **OK**.</span></span>
63. <span data-ttu-id="010c0-188">Fare clic su **Aggiungi elemento**.</span><span class="sxs-lookup"><span data-stu-id="010c0-188">Click **Add Element**.</span></span>
64. <span data-ttu-id="010c0-189">Nel campo Nome digitare **Importo**.</span><span class="sxs-lookup"><span data-stu-id="010c0-189">In the Name field, type **Amount**.</span></span>
65. <span data-ttu-id="010c0-190">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="010c0-190">Click **OK**.</span></span>

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a><span data-ttu-id="010c0-191">Preparare i componenti del formato per eseguire il mapping a elementi del modello dati</span><span class="sxs-lookup"><span data-stu-id="010c0-191">Prepare format components for mapping to data model elements</span></span>
1. <span data-ttu-id="010c0-192">Nella struttura selezionare **Xml\Messaggio\ProcessingDate**.</span><span class="sxs-lookup"><span data-stu-id="010c0-192">In the tree, select **Xml\Message\ProcessingDate**.</span></span>
2. <span data-ttu-id="010c0-193">Fare clic su **Aggiungi** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="010c0-193">Click **Add** to open the drop dialog.</span></span>
3. <span data-ttu-id="010c0-194">Nella struttura selezionare **Text\DateTime**.</span><span class="sxs-lookup"><span data-stu-id="010c0-194">In the tree, select **Text\DateTime**.</span></span>
4. <span data-ttu-id="010c0-195">Nel campo **Formato** digitare **gg-MM-aaaa**.</span><span class="sxs-lookup"><span data-stu-id="010c0-195">In the **Format** field, type **yyyy-MM-dd**.</span></span>
5. <span data-ttu-id="010c0-196">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="010c0-196">Click **OK**.</span></span>
6. <span data-ttu-id="010c0-197">Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\TransDate**.</span><span class="sxs-lookup"><span data-stu-id="010c0-197">In the tree, select **Xml\Message\Payments\Item\TransDate**.</span></span>
7. <span data-ttu-id="010c0-198">Fare clic su **Aggiungi DateTime**.</span><span class="sxs-lookup"><span data-stu-id="010c0-198">Click **Add DateTime**.</span></span>
8. <span data-ttu-id="010c0-199">Nel campo **Formato** digitare **gg-MM-aaaa**.</span><span class="sxs-lookup"><span data-stu-id="010c0-199">In the **Format** field, type **yyyy-MM-dd**.</span></span>
9. <span data-ttu-id="010c0-200">Nel campo **DateTime** selezionare **Date**.</span><span class="sxs-lookup"><span data-stu-id="010c0-200">In the **DateTime** type field, select **Date**.</span></span>
10. <span data-ttu-id="010c0-201">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="010c0-201">Click **OK**.</span></span>
11. <span data-ttu-id="010c0-202">Nella struttura selezionare **Xml\Messaggio\MessageId**.</span><span class="sxs-lookup"><span data-stu-id="010c0-202">In the tree, select **Xml\Message\MessageId**.</span></span>
12. <span data-ttu-id="010c0-203">Fare clic su **Aggiungi** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="010c0-203">Click **Add** to open the drop dialog.</span></span>
13. <span data-ttu-id="010c0-204">Nella struttura selezionare **Testo\Stringa**.</span><span class="sxs-lookup"><span data-stu-id="010c0-204">In the tree, select **Text\String**.</span></span>
14. <span data-ttu-id="010c0-205">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="010c0-205">Click **OK**.</span></span>
15. <span data-ttu-id="010c0-206">Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\Fornitore\Nome**.</span><span class="sxs-lookup"><span data-stu-id="010c0-206">In the tree, select **Xml\Message\Payments\Item\Vendor\Name**.</span></span>
16. <span data-ttu-id="010c0-207">Fare clic su **Aggiungi stringa**.</span><span class="sxs-lookup"><span data-stu-id="010c0-207">Click **Add String**.</span></span>
17. <span data-ttu-id="010c0-208">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="010c0-208">Click **OK**.</span></span>
18. <span data-ttu-id="010c0-209">Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\Fornitore\Banca\RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="010c0-209">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber**.</span></span>
19. <span data-ttu-id="010c0-210">Fare clic su **Aggiungi stringa**.</span><span class="sxs-lookup"><span data-stu-id="010c0-210">Click **Add String**.</span></span>
20. <span data-ttu-id="010c0-211">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="010c0-211">Click **OK**.</span></span>
21. <span data-ttu-id="010c0-212">Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\Fornitore\Banca\AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="010c0-212">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank\AccountNumber**.</span></span>
22. <span data-ttu-id="010c0-213">Fare clic su **Aggiungi stringa**.</span><span class="sxs-lookup"><span data-stu-id="010c0-213">Click **Add String**.</span></span>
23. <span data-ttu-id="010c0-214">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="010c0-214">Click **OK**.</span></span>
24. <span data-ttu-id="010c0-215">Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\Pagante\Nome**.</span><span class="sxs-lookup"><span data-stu-id="010c0-215">In the tree, select **Xml\Message\Payments\Item\Payer\Name**.</span></span>
25. <span data-ttu-id="010c0-216">Fare clic su **Aggiungi stringa**.</span><span class="sxs-lookup"><span data-stu-id="010c0-216">Click **Add String**.</span></span>
26. <span data-ttu-id="010c0-217">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="010c0-217">Click **OK**.</span></span>
27. <span data-ttu-id="010c0-218">Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\Pagante\Banca\RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="010c0-218">In the tree, select **Xml\Message\Payments\Item\Payer\Bank\RoutingNumber**.</span></span>
28. <span data-ttu-id="010c0-219">Fare clic su **Aggiungi stringa**.</span><span class="sxs-lookup"><span data-stu-id="010c0-219">Click **Add String**.</span></span>
29. <span data-ttu-id="010c0-220">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="010c0-220">Click **OK**.</span></span>
30. <span data-ttu-id="010c0-221">Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\Pagante\Banca\AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="010c0-221">In the tree, select **Xml\Message\Payments\Item\Payer\Bank\AccountNumber**.</span></span>
31. <span data-ttu-id="010c0-222">Fare clic su **Aggiungi stringa**.</span><span class="sxs-lookup"><span data-stu-id="010c0-222">Click **Add String**.</span></span>
32. <span data-ttu-id="010c0-223">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="010c0-223">Click **OK**.</span></span>
33. <span data-ttu-id="010c0-224">Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\Valuta**.</span><span class="sxs-lookup"><span data-stu-id="010c0-224">In the tree, select **Xml\Message\Payments\Item\Currency**.</span></span>
34. <span data-ttu-id="010c0-225">Fare clic su **Aggiungi stringa**.</span><span class="sxs-lookup"><span data-stu-id="010c0-225">Click **Add String**.</span></span>
35. <span data-ttu-id="010c0-226">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="010c0-226">Click **OK**.</span></span>
36. <span data-ttu-id="010c0-227">Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="010c0-227">In the tree, select **Xml\Message\Payments\Item\Description**.</span></span>
37. <span data-ttu-id="010c0-228">Fare clic su **Aggiungi stringa**.</span><span class="sxs-lookup"><span data-stu-id="010c0-228">Click **Add String**.</span></span>
38. <span data-ttu-id="010c0-229">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="010c0-229">Click **OK**.</span></span>
39. <span data-ttu-id="010c0-230">Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\Importo**.</span><span class="sxs-lookup"><span data-stu-id="010c0-230">In the tree, select **Xml\Message\Payments\Item\Amount**.</span></span>
40. <span data-ttu-id="010c0-231">Fare clic su **Aggiungi stringa**.</span><span class="sxs-lookup"><span data-stu-id="010c0-231">Click **Add String**.</span></span>
41. <span data-ttu-id="010c0-232">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="010c0-232">Click **OK**.</span></span>
42. <span data-ttu-id="010c0-233">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="010c0-233">Click **Save**.</span></span>
43. <span data-ttu-id="010c0-234">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="010c0-234">Close the page.</span></span>

