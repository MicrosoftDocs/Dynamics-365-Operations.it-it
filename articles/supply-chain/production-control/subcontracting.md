---
title: Conto lavoro
description: In questo argomento vengono fornite le informazioni dettagliate per creare un conto lavoro nella produzione in Dynamics 365 Supply Chain Management.
author: christophernread
manager: tfehr
ms.date: 09/28/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2018-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 05e6ccdce21ccc5f3e83ad860163cccadcea2edc
ms.sourcegitcommit: ffd845d4230646499b6f074cb43e69ab95787671
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "3346424"
---
# <a name="subcontracting"></a><span data-ttu-id="98201-103">Conto lavoro</span><span class="sxs-lookup"><span data-stu-id="98201-103">Subcontracting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="98201-104">In questo argomento vengono fornite le informazioni dettagliate per creare un conto lavoro nella produzione in Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="98201-104">This topic will help you build a walkthrough of subcontracting in manufacturing in Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="98201-105">La prima parte di questo argomento descrive l'impostazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="98201-105">The first part of this topic describes the setup of the data.</span></span> <span data-ttu-id="98201-106">La seconda parte descrive la procedura.</span><span class="sxs-lookup"><span data-stu-id="98201-106">The second part takes you through the steps in the walkthrough.</span></span>

## <a name="target-audience"></a><span data-ttu-id="98201-107">Destinatari</span><span class="sxs-lookup"><span data-stu-id="98201-107">Target audience</span></span>

<span data-ttu-id="98201-108">Questo argomento descrive come impostare il conto lavoro nella produzione.</span><span class="sxs-lookup"><span data-stu-id="98201-108">In this topic, you will learn how to set up subcontracting in manufacturing.</span></span> <span data-ttu-id="98201-109">Verranno usati i dati esistenti nella persona giuridica HQUS per eseguire l'impostazione di base di un flusso di attività conto lavoro.</span><span class="sxs-lookup"><span data-stu-id="98201-109">You will use existing data in the HQUS legal entity to do the basic setup of a subcontracting activity flow.</span></span> <span data-ttu-id="98201-110">I dati dimostrativi nella persona giuridica HQUS includono i parametri di impostazione che sono stati prestabiliti per supportare i passaggi della procedura.</span><span class="sxs-lookup"><span data-stu-id="98201-110">The demo data in the HQUS legal entity includes setup parameters that have been preset to support the steps in the walkthrough.</span></span> <span data-ttu-id="98201-111">Anche se la procedura risolve i punti critici e le sfide per vari ruoli, può essere completata dall'amministratore di sistema.</span><span class="sxs-lookup"><span data-stu-id="98201-111">Even though the walkthrough addresses key pain points and challenges for various roles, it can be completed by the system admin.</span></span>

## <a name="demo-scenario"></a><span data-ttu-id="98201-112">Scenario dimostrativo</span><span class="sxs-lookup"><span data-stu-id="98201-112">Demo scenario</span></span>

<span data-ttu-id="98201-113">Nella persona giuridica HQUS vengono prodotti alto parlanti di fascia alta.</span><span class="sxs-lookup"><span data-stu-id="98201-113">In the HQUS legal entity, high-end speakers are manufactured.</span></span> <span data-ttu-id="98201-114">Durante il processo di produzione gli altoparlanti subiscono tre operazioni.</span><span class="sxs-lookup"><span data-stu-id="98201-114">During the manufacturing process, speakers go through the following three operations.</span></span>

- <span data-ttu-id="98201-115">**Preassemblaggio** - Viene assemblato il cabinet dell'altoparlante.</span><span class="sxs-lookup"><span data-stu-id="98201-115">**Pre-assembly** – The speaker cabinet is assembled.</span></span> <span data-ttu-id="98201-116">Il materiale per il cabinet viene prelevato dal magazzino prima che abbia inizio l'operazione.</span><span class="sxs-lookup"><span data-stu-id="98201-116">The material for the cabinet is picked in the material warehouse before the operation is started.</span></span>
- <span data-ttu-id="98201-117">**Rivestimento** - Dopo l'assemblaggio, il cabinet viene rivestito.</span><span class="sxs-lookup"><span data-stu-id="98201-117">**Coating** – After the speaker cabinet has been assembled, it must be coated.</span></span> <span data-ttu-id="98201-118">Questa operazione viene completata da un fornitore (terzista).</span><span class="sxs-lookup"><span data-stu-id="98201-118">This operation is completed by a vendor (subcontractor).</span></span> <span data-ttu-id="98201-119">Il cabinet dell'altoparlante preassemblato viene spedito al terzista che si occupa del rivestimento insieme a due materiali.</span><span class="sxs-lookup"><span data-stu-id="98201-119">The pre-assembled speaker cabinet is shipped to the coating subcontractor together with two materials.</span></span>
- <span data-ttu-id="98201-120">**Finitura** - Dopo essere stato assemblato e rivestito dal terzista, il cabinet torna alla persona giuridica HQUS per completare l'assemblaggio finale dell'altoparlante.</span><span class="sxs-lookup"><span data-stu-id="98201-120">**Finish** – After the pre-assembled speaker cabinet has been coated by the subcontractor, it's returned to the HQUS legal entity so that final assembly of the speaker can be completed.</span></span>

<span data-ttu-id="98201-121">La figura seguente mostra le tre operazioni e i materiali impiegati.</span><span class="sxs-lookup"><span data-stu-id="98201-121">The following illustration shows the three operations and the materials that they consume.</span></span>

![Operazioni di preassemblaggio, rivestimento e finitura e i materiali impiegati](./media/subcontract01_operations-materials.png)

## <a name="setup"></a><span data-ttu-id="98201-123">Imposta</span><span class="sxs-lookup"><span data-stu-id="98201-123">Setup</span></span>

<span data-ttu-id="98201-124">Prima di iniziare la procedura, è necessario impostare i dati.</span><span class="sxs-lookup"><span data-stu-id="98201-124">Before you start the walkthrough, you must set up the data.</span></span>

### <a name="set-up-the-finished-product"></a><span data-ttu-id="98201-125">Impostare il prodotto finito</span><span class="sxs-lookup"><span data-stu-id="98201-125">Set up the finished product</span></span>

<span data-ttu-id="98201-126">Questa procedura illustra l'impostazione del prodotto rilasciato D8100, "Cabinet rivestito".</span><span class="sxs-lookup"><span data-stu-id="98201-126">This procedure takes you through the setup of released product D8100, "Coated Cabinet."</span></span>

1. <span data-ttu-id="98201-127">Selezionare **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati** per aprire la pagina **Dettagli prodotto rilasciato**.</span><span class="sxs-lookup"><span data-stu-id="98201-127">Select **Product information management \> Products \> Released products** to open the **Released product details** page.</span></span>
2. <span data-ttu-id="98201-128">Nel campo del filtro rapido, immettere **D8100** per trovare il prodotto rilasciato esistente.</span><span class="sxs-lookup"><span data-stu-id="98201-128">In the quick filter field, enter **D8100** to find the existing released product.</span></span>

    ![Filtro per il prodotto rilasciato D8100 nella pagina dei dettagli del prodotto rilasciato](./media/subcontract02_filtering-released-products.png)

3. <span data-ttu-id="98201-130">Nel riquadro azioni, nella scheda **Progetta** selezionare **Ciclo** per aprire la pagina **Ciclo di lavorazione**.</span><span class="sxs-lookup"><span data-stu-id="98201-130">On the Action Pane, on the **Engineer** tab, select **Route** to open the **Route** page.</span></span>

    <span data-ttu-id="98201-131">La pagina **Ciclo di lavorazione** mostra le otto versioni del ciclo per il prodotto rilasciato D8100.</span><span class="sxs-lookup"><span data-stu-id="98201-131">The **Route** page shows the eight route versions for released product D8100.</span></span> <span data-ttu-id="98201-132">Le otto versioni del ciclo di lavorazione sono suddivise in quattro cicli di lavorazione nel sito 1 e nel sito 5.</span><span class="sxs-lookup"><span data-stu-id="98201-132">The eight route versions are divided among four routes on site 1 and site 5.</span></span> <span data-ttu-id="98201-133">Il ciclo di lavorazione 000400 viene utilizzato per la determinazione dei costi, il ciclo 00041 viene utilizzato quando l'operazione di rivestimento avviene internamento e il ciclo 00042 viene utilizzando quando tale operazione avviene esternamente.</span><span class="sxs-lookup"><span data-stu-id="98201-133">Route 000400 is used for costing, route 00041 is used when the Coating operation is an internal operation, and route 00042 is used when the Coating operation is an external operation.</span></span>

    ![Otto versioni del ciclo di lavorazione nella pagina Ciclo di lavorazione](./media/subcontract03_route-page.png)

4. <span data-ttu-id="98201-135">Nel riquadro superiore, nella griglia **Versioni** selezionare la versione **00042** per il sito **5**.</span><span class="sxs-lookup"><span data-stu-id="98201-135">In the upper pane, in the **Versions** grid, select route version **00042** for site **5**.</span></span>
5. <span data-ttu-id="98201-136">Nel riquadro inferiore, nella scheda **Panoramica** selezionare l'operazione **20** (**Cbnt CtSc**) nella griglia.</span><span class="sxs-lookup"><span data-stu-id="98201-136">In the lower pane, on the **Overview** tab, select operation **20** (**Cbnt CtSc**) in the grid.</span></span>

    ![Operazione 20 per la versione 00042 del sito 5 selezionata](./media/subcontract04_route-version-operation.png)

6. <span data-ttu-id="98201-138">Selezionare la scheda **Generale**.</span><span class="sxs-lookup"><span data-stu-id="98201-138">Select the **General** tab.</span></span>

    <span data-ttu-id="98201-139">Notare che il campo **Tipo ciclo di lavorazione** è impostato su **Fornitore**.</span><span class="sxs-lookup"><span data-stu-id="98201-139">Notice that the field **Route type** field is set to **Vendor**.</span></span> <span data-ttu-id="98201-140">Questo valore indica che l'operazione 20 (Cbnt CtSc) costituisce un'operazione in conto lavoro.</span><span class="sxs-lookup"><span data-stu-id="98201-140">This value indicates that operation 20 (Cbnt CtSc) is a subcontracted operation.</span></span>

    ![Campo Tipo di lavorazione impostato su Fornitore nella scheda Generale](./media/subcontract05_general-tab.png)

7. <span data-ttu-id="98201-142">Selezionare la scheda **Requisiti risorsa**.</span><span class="sxs-lookup"><span data-stu-id="98201-142">Select the **Resource requirements** tab.</span></span>

    <span data-ttu-id="98201-143">Le funzionalità verranno utilizzate per trovare una risorsa valida durante la programmazione della produzione.</span><span class="sxs-lookup"><span data-stu-id="98201-143">Capabilities will be used to find an applicable resource during production scheduling.</span></span> <span data-ttu-id="98201-144">Per l'operazione 20 (Cbnt CtSc), notare che è necessaria una risorsa che abbia due funzionalità, **Rivestimento** e **Cabinet rivestiti**.</span><span class="sxs-lookup"><span data-stu-id="98201-144">For operation 20 (Cbnt CtSc), notice that a resource that has two capabilities, **Coating** and **Coated cabinets**, is required.</span></span>

    ![Funzionalità Rivestimento e Cabinet rivestiti nella scheda dei requisiti di risorsa](./media/subcontract06_resource-requirements-tab.png)

8. <span data-ttu-id="98201-146">Selezionare **Risorse applicabili** per aprire la finestra di dialogo **Risorse applicabili**.</span><span class="sxs-lookup"><span data-stu-id="98201-146">Select **Applicable resources** to open the **Applicable resources** dialog box.</span></span>

    <span data-ttu-id="98201-147">Tre risorse sono disponibili che soddisfano i requisiti di risorsa per l'operazione.</span><span class="sxs-lookup"><span data-stu-id="98201-147">Three resources are found that match the resource requirements for the operation.</span></span> <span data-ttu-id="98201-148">Notare che le risorse 8851 e 8852 sono di tipo **Fornitore**.</span><span class="sxs-lookup"><span data-stu-id="98201-148">Notice that resources 8851 and 8852 are of the **Vendor** type.</span></span>

    ![Tre risorse appropriate nella finestra di dialogo Risorse applicabili](./media/subcontract07_applicable-resources-dialog.png)

9. <span data-ttu-id="98201-150">Selezionare **OK** per chiudere la finestra di dialogo **Risorse applicabili** e tornare alla pagina **Ciclo di lavorazione**.</span><span class="sxs-lookup"><span data-stu-id="98201-150">Select **OK** to close the **Applicable resources** dialog box and return to the **Route** page.</span></span>
10. <span data-ttu-id="98201-151">Chiudere la pagina **Ciclo di lavorazione** per tornare alla pagina **Dettagli prodotto rilasciato**.</span><span class="sxs-lookup"><span data-stu-id="98201-151">Close the **Route** page to return to the **Released product details** page.</span></span>

    ![Pagina Dettagli prodotto rilasciato](./media/subcontract08_released-product-details-page.png)

11. <span data-ttu-id="98201-153">Nel riquadro azioni, nella scheda **Progetta** selezionare **Versioni DBA** per aprire la pagina **Versioni DBA**.</span><span class="sxs-lookup"><span data-stu-id="98201-153">On the Action Pane, on the **Engineer** tab, select **BOM versions** to open the **BOM versions** page.</span></span>

    <span data-ttu-id="98201-154">La pagina **Versioni DBA** mostra le quattro versioni di distinta base (DBA) per il prodotto rilasciato D8100.</span><span class="sxs-lookup"><span data-stu-id="98201-154">The **BOM versions** page shows the four bill of materials (BOM) versions for released product D8100.</span></span> <span data-ttu-id="98201-155">La DBA 000040 viene utilizzata per la determinazione dei costi e la pianificazione, la DBA 000041 viene utilizzata se l'operazione Rivestimento viene effettuata internamente e le DBA 000042 e 000043 vengono utilizzate se l'operazione Rivestimento è in conto lavoro.</span><span class="sxs-lookup"><span data-stu-id="98201-155">BOM 000040 is used for costing and planning, BOM 000041 is used if the Coating operation is done in-house, and BOMs 000042 and 000043 are used if the Coating operation is subcontracted.</span></span>

    <span data-ttu-id="98201-156">Si noti che l'articolo S8050 è un prodotto di tipo **Servizio**.</span><span class="sxs-lookup"><span data-stu-id="98201-156">Notice that item S8050 is a product of the **Service** item type.</span></span> <span data-ttu-id="98201-157">Questo articolo rappresenta il lavoro in conto lavoro.</span><span class="sxs-lookup"><span data-stu-id="98201-157">This item represents the subcontracted work.</span></span>

    ![Quattro versioni di DBA nella pagina Versioni DBA](./media/subcontract09_bom-versions-page.png)

12. <span data-ttu-id="98201-159">Nella Scheda dettaglio **Righe della distinta base** selezionare **Modifica** per aprire la finestra di dialogo **Modifica riga DBA**.</span><span class="sxs-lookup"><span data-stu-id="98201-159">On the **Bill of materials lines** FastTab, select **Edit** to open the **Edit BOM line** dialog box.</span></span>

    <span data-ttu-id="98201-160">Quando viene creato e stimato un ordine di produzione per il prodotto rilasciato D8100, viene generato automaticamente un ordine fornitore per l'articolo S8050.</span><span class="sxs-lookup"><span data-stu-id="98201-160">When a production order is created and estimated for released product D8100, a purchase order will be automatically generated for item S8050.</span></span> <span data-ttu-id="98201-161">L'ordine fornitore verrà collegato all'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="98201-161">This purchase order will be linked to the production order.</span></span> <span data-ttu-id="98201-162">Affinché gli ordini fornitore vengano generati automaticamente, è necessario impostare il campo **Tipo di riga** su **Fornitore** e selezionare il conto fornitore per il terzista.</span><span class="sxs-lookup"><span data-stu-id="98201-162">For purchase orders to be automatically generated, the **Line type** field must be set to **Vendor**, and the vendor account for the subcontractor must be selected.</span></span> <span data-ttu-id="98201-163">In questo caso il conto fornitore è US-801.</span><span class="sxs-lookup"><span data-stu-id="98201-163">In this case, the vendor account is US-801.</span></span>

    <span data-ttu-id="98201-164">Notare che la riga DBA è collegata all'operazione Rivestimento tramite il numero di operazione, in questo caso 20.</span><span class="sxs-lookup"><span data-stu-id="98201-164">Notice that the BOM line is connected to the Coating operation through the operation number (in this case, 20).</span></span>

    ![Finestra di dialogo Modifica riga DBA](./media/subcontract10_edit-bom-line-dialog.png)

### <a name="create-a-password-for-warehouse-workers"></a><span data-ttu-id="98201-166">Creare una password per gli addetti magazzino</span><span class="sxs-lookup"><span data-stu-id="98201-166">Create a password for warehouse workers</span></span>

<span data-ttu-id="98201-167">È necessario definire una password per gli addetti magazzino che utilizzano il dispositivo palmare.</span><span class="sxs-lookup"><span data-stu-id="98201-167">You must define a password for the warehouse workers who use the hand-held device.</span></span>

1. <span data-ttu-id="98201-168">Selezionare **Gestione magazzino \> Impostazioni \> Lavoratore** per aprire la pagina **Utenti di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="98201-168">Select **Warehouse management \> Setup \> Worker** to open the **Work users** page.</span></span>
2. <span data-ttu-id="98201-169">Nella Scheda dettaglio **Utenti** selezionare la riga per l'utente **51**.</span><span class="sxs-lookup"><span data-stu-id="98201-169">On the **Users** FastTab, select the row for user **51**.</span></span>

    ![Pagina Utenti di lavoro](./media/subcontract11_work-users-page.png)

3. <span data-ttu-id="98201-171">Selezionare **Reimposta password**.</span><span class="sxs-lookup"><span data-stu-id="98201-171">Select **Reset password**.</span></span>
4. <span data-ttu-id="98201-172">Nei campi **Password** e **Conferma password** immettere **1**.</span><span class="sxs-lookup"><span data-stu-id="98201-172">In the **Password** and **Confirm password** fields, enter **1**.</span></span>
5. <span data-ttu-id="98201-173">Selezionare **Imposta password**.</span><span class="sxs-lookup"><span data-stu-id="98201-173">Select **Set password**.</span></span>

## <a name="step-by-step-walkthrough"></a><span data-ttu-id="98201-174">Procedura</span><span class="sxs-lookup"><span data-stu-id="98201-174">Step-by-step walkthrough</span></span>

<span data-ttu-id="98201-175">**Scenario e sfondo**</span><span class="sxs-lookup"><span data-stu-id="98201-175">**Scenario and background**</span></span>

<span data-ttu-id="98201-176">Viene creato un ordine di produzione di 10 pezzi per il prodotto D8100, "Cabinet rivestito".</span><span class="sxs-lookup"><span data-stu-id="98201-176">A production order of 10 pieces is created for product D8100, "Coated Cabinet."</span></span> <span data-ttu-id="98201-177">Il rivestimento dei cabinet è un'operazione in conto lavoro che viene eseguita presso il fornitore US-801, Perfect Coating Solutions.</span><span class="sxs-lookup"><span data-stu-id="98201-177">The coating of the cabinets is a sub-contracted operation that is done at vendor US-801, Perfect Coating Solutions.</span></span> <span data-ttu-id="98201-178">L'ordine di produzione è costituito da tre operazioni.</span><span class="sxs-lookup"><span data-stu-id="98201-178">The production order consists of three operations.</span></span> <span data-ttu-id="98201-179">Nella prima operazione il gabinetto viene preassemblato internamente.</span><span class="sxs-lookup"><span data-stu-id="98201-179">In the first operation, the cabinet is pre-assembled as an in-house operation.</span></span> <span data-ttu-id="98201-180">Il materiale per il pre-assemblaggio viene rilasciato per essere prelevato nel magazzino delle materie prime.</span><span class="sxs-lookup"><span data-stu-id="98201-180">The material for the pre-assembly is released for picking in the raw material warehouse.</span></span> <span data-ttu-id="98201-181">Dopo l'assemblaggio, il cabine viene inviato a Perfect Coating Solutions insieme a due materiali che sono necessari per l'operazione di rivestimento.</span><span class="sxs-lookup"><span data-stu-id="98201-181">After the pre-assembly is completed, the pre-assembled cabinet is sent to Perfect Coating Solutions together with two materials that are required for the Coating operation.</span></span> <span data-ttu-id="98201-182">Quando il cabinet rivestito viene restituito dal fornitore, viene sottoposto internamente a un'operazione di assemblaggio finale prima di essere segnalato come finito.</span><span class="sxs-lookup"><span data-stu-id="98201-182">When the coated cabinet is received back from the vendor, it goes through a final in-house assembly operation before it's reported as finished.</span></span>

1. <span data-ttu-id="98201-183">Selezionare **Controllo produzione \> Ordini di produzione \> Tutti gli ordini di produzione** per aprire la pagina **Tutti gli ordini di produzione**.</span><span class="sxs-lookup"><span data-stu-id="98201-183">Select **Production control \> Production orders \> All production orders** to open the **All production orders** page.</span></span>
2. <span data-ttu-id="98201-184">Nel riquadro azioni selezionare **Nuovo ordine di produzione** per aprire la finestra di dialogo **Crea ordine di produzione**.</span><span class="sxs-lookup"><span data-stu-id="98201-184">On the Action Pane, select **New production order** to open the **Create production order** dialog box.</span></span>

    ![Finestra di dialogo Crea ordine di produzione](./media/subcontract12_create-production-order-dialog.png)

3. <span data-ttu-id="98201-186">Nel campo **Numero articolo** selezionare **D8100**.</span><span class="sxs-lookup"><span data-stu-id="98201-186">In the **Item number** field, select **D8100**.</span></span>
4. <span data-ttu-id="98201-187">Dopo avere selezionare il numero articolo, vengono visualizzati i campi per le dimensioni inventariali.</span><span class="sxs-lookup"><span data-stu-id="98201-187">After you select the item number, fields for the inventory dimensions appear.</span></span> <span data-ttu-id="98201-188">Nel campo **Colore** selezionare **Cromato**.</span><span class="sxs-lookup"><span data-stu-id="98201-188">In the **Color** field, select **Chrome**.</span></span>

    <span data-ttu-id="98201-189">Verrà visualizzata una finestra di messaggio per chiedere se è necessario inserire le versioni attive della DBA e del ciclo di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="98201-189">A message box appears that asks whether the active versions for the BOM and route should be inserted.</span></span>

    ![Finestra di messaggio](./media/subcontract13_message-box.png)

5. <span data-ttu-id="98201-191">Selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="98201-191">Select **Yes**.</span></span> 

    <span data-ttu-id="98201-192">Nella finestra di dialogo **Crea ordine di produzione** le versioni attive della DBA e del ciclo di lavorazione per il prodotto D8100 vengono automaticamente selezionate nei rispettivi campi **Numero DBA** e **Numero ciclo di lavorazione**.</span><span class="sxs-lookup"><span data-stu-id="98201-192">In the **Create production order** dialog box, the active versions of the BOM and route for product D8100 are automatically selected in the **BOM number** and **Route number** fields, respectively.</span></span> <span data-ttu-id="98201-193">In questo caso vengono selezionati la DBA **000040** e il ciclo di lavorazione **000040**.</span><span class="sxs-lookup"><span data-stu-id="98201-193">In this case, BOM **000040** and route **000040** are selected.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="98201-194">Sia per la DBA che per il ciclo di lavorazione, viene utilizzata la versione 000040 per la determinazione dei costi e la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="98201-194">For both the BOM and the route, version 000040 is used for costing and planning.</span></span>

6. <span data-ttu-id="98201-195">Nel campo **Sito** selezionare **5**.</span><span class="sxs-lookup"><span data-stu-id="98201-195">In the **Site** field, select **5**.</span></span>
7. <span data-ttu-id="98201-196">Nel campo **Magazzino** selezionare **51**.</span><span class="sxs-lookup"><span data-stu-id="98201-196">In the **Warehouse** field, select **51**.</span></span>
8. <span data-ttu-id="98201-197">Nei campi **Numero DBA** e **Numero ciclo di lavorazione** modificare il valore selezionato automaticamente in **000042**.</span><span class="sxs-lookup"><span data-stu-id="98201-197">In the **BOM number** and **Route number** fields, change the value that was automatically selected to **000042**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="98201-198">Sia per la DBA che per il ciclo di lavorazione, viene utilizzata la versione 000042 per subappaltare l'operazione di rivestimento del cabinet al fornitore US-801.</span><span class="sxs-lookup"><span data-stu-id="98201-198">For both the BOM and the route, version 000042 is used to subcontract the coating of the cabinet to vendor US-801.</span></span>

    ![Valori impostati nella finestra di dialogo Crea ordine di produzione](./media/subcontract14_create-production-order-dialog-set.png)

9. <span data-ttu-id="98201-200">Selezionare **Crea** per creare l'ordine di produzione e tornare alla pagina **Tutti gli ordini di produzione**.</span><span class="sxs-lookup"><span data-stu-id="98201-200">Select **Create** to create the production order and return to the **All production orders** page.</span></span>

    ![Nuovo ordine di produzione nella pagina Tutti gli ordini di produzione](./media/subcontract15_new-production-order.png)

10. <span data-ttu-id="98201-202">Nel riquadro azioni, nella scheda **Ordine di produzione** selezionare **Stima** per aprire la finestra di dialogo **Stima**.</span><span class="sxs-lookup"><span data-stu-id="98201-202">On the Action Pane, on the **Production order** tab, select **Estimate** to open the **Estimate** dialog box.</span></span>

    ![Finestra di dialogo Stima](./media/subcontract16_estimate-dialog.png)

11. <span data-ttu-id="98201-204">Selezionare **OK** per confermare la stima e tornare alla pagina **Tutti gli ordini di produzione**.</span><span class="sxs-lookup"><span data-stu-id="98201-204">Select **OK** to confirm the estimate and return to the **All production orders** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="98201-205">Dopo la stima dell'ordine di produzione, viene generato l'ordine fornitore per l'articolo di tipo Assistenza S8050 per il fornitore US-801.</span><span class="sxs-lookup"><span data-stu-id="98201-205">When the production order is estimated, the purchase order for service item S8050 is generated for vendor US-801.</span></span>

12. <span data-ttu-id="98201-206">Nel riquadro azioni, nella scheda **Ordine di produzione** selezionare **DBA** per aprire la pagina **DBA**, dove è possibile visualizzare le righe DBA per l'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="98201-206">On the Action Pane, on the **Production order** tab, select **BOM** to open the **BOM** page, where you can view the BOM lines for the production order.</span></span>

    <span data-ttu-id="98201-207">Per l'articolo di tipo Assistenza S8050, notare che è presente un riferimento all'ordine fornitore generato quando l'ordine di produzione è stato stimato.</span><span class="sxs-lookup"><span data-stu-id="98201-207">For service item S8050, notice that there is a reference to the purchase order that was generated when the production order was estimated.</span></span>

    ![Righe DBA dell'ordine di produzione nella pagina DBA](./media/subcontract17_production-order-bom-lines.png)

13. <span data-ttu-id="98201-209">Chiudere la pagina **DBA** per tornare alla pagina **Tutti gli ordini di produzione**.</span><span class="sxs-lookup"><span data-stu-id="98201-209">Close the **BOM** page to return to the **All production orders** page.</span></span>
14. <span data-ttu-id="98201-210">Nel riquadro azioni, nella scheda **Programma** selezionare **Programma processi** per aprire la finestra di dialogo **Programmazione processo**.</span><span class="sxs-lookup"><span data-stu-id="98201-210">On the Action Pane, on the **Schedule** tab, select **Schedule jobs** to open the **Job scheduling** dialog box.</span></span>
15. <span data-ttu-id="98201-211">Specificare i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="98201-211">Specify the following values:</span></span>

    - <span data-ttu-id="98201-212">Nel campo **Direzione programmazione** selezionare **Avanti da domani**.</span><span class="sxs-lookup"><span data-stu-id="98201-212">In the **Scheduling direction** field, select **Forward from tomorrow**.</span></span>
    - <span data-ttu-id="98201-213">Impostare l'opzione **Capacità limitata** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="98201-213">Set the **Finite capacity** option to **Yes**.</span></span>

    ![Finestra di dialogo Programmazione processi](./media/subcontract18_job-scheduling-dialog.png)

16. <span data-ttu-id="98201-215">Selezionare **OK** per chiudere la finestra di dialogo **Programmazione processi** e tornare alla pagina **Tutti gli ordini di produzione**.</span><span class="sxs-lookup"><span data-stu-id="98201-215">Select **OK** to close the **Job scheduling** dialog box and return to the **All production orders** page.</span></span>
17. <span data-ttu-id="98201-216">Nel riquadro azioni, nella scheda **Programma** scegliere **Gantt** per aprire la pagina **Diagramma di Gantt - visualizzazione risorse**.</span><span class="sxs-lookup"><span data-stu-id="98201-216">On the Action Pane, on the **Schedule** tab, select **Gantt** to open the **Gantt chart - Resource view** page.</span></span>

    <span data-ttu-id="98201-217">Il diagramma di Gantt fornisce una panoramica visiva del modo in cui i processi di produzione vengono programmati sulle risorse.</span><span class="sxs-lookup"><span data-stu-id="98201-217">The Gantt chart provides a visual overview of how the production jobs are scheduled on the resources.</span></span> <span data-ttu-id="98201-218">Notare che l'operazione esterna di rivestimento consiste in tre processi: un processo di lavorazione, un processo di trasporto e un processo con tempo di attesa.</span><span class="sxs-lookup"><span data-stu-id="98201-218">Notice that the external Coating operation consists of three jobs: a process job, a transport job, and a queue time job.</span></span>

    ![Pagina Diagramma di Gantt - Visualizzazione risorse](./media/subcontract19_gantt-chart.png)

18. <span data-ttu-id="98201-220">Chiudere la pagina **Diagramma di Gantt - Visualizzazione risorse** per tornare alla pagina **Tutti gli ordini di produzione**.</span><span class="sxs-lookup"><span data-stu-id="98201-220">Close the **Gantt chart - Resource view** page to return to the **All production orders** page.</span></span>
19. <span data-ttu-id="98201-221">Nel riquadro azioni, nella scheda **Ordine di produzione** selezionare **Rilascio** per aprire la finestra di dialogo **Rilascio**.</span><span class="sxs-lookup"><span data-stu-id="98201-221">On the Action Pane, on the **Production order** tab, select **Release** to open the **Release** dialog box.</span></span>

    ![Finestra di dialogo Rilascio](./media/subcontract20_release-dialog.png)

20. <span data-ttu-id="98201-223">Selezionare **OK** per chiudere la finestra di dialogo **Rilascio**.</span><span class="sxs-lookup"><span data-stu-id="98201-223">Select **OK** to close the **Release** dialog box.</span></span>
21. <span data-ttu-id="98201-224">Selezionare **Controllo produzione \> Attività periodiche \> Rilascia in magazzino \> Rilascio automatico di righe di DBA e di formula** per aprire la finestra di dialogo **Rilascio automatico di righe di DBA e di formula**.</span><span class="sxs-lookup"><span data-stu-id="98201-224">Select **Production control \> Periodic tasks \> Release to warehouse \> Automatic release of BOM and formula lines** to open the **Automatic release of BOM and formula lines** dialog box.</span></span>

    ![Finestra di dialogo Rilascio automatico di righe di DBA e di formula](./media/subcontract21_auto-release-bom-formula-lines-dialog.png)

22. <span data-ttu-id="98201-226">Selezionare **OK** per eseguire il processo Rilascio automatico di righe di DBA e di formula.</span><span class="sxs-lookup"><span data-stu-id="98201-226">Select **OK** to run the Automatic release of BOM and formula lines job.</span></span>

    <span data-ttu-id="98201-227">Questo processo rilascia il lavoro di prelievo delle materie prime al magazzino.</span><span class="sxs-lookup"><span data-stu-id="98201-227">This job releases pick work for raw materials to the warehouse.</span></span>

23. <span data-ttu-id="98201-228">Selezionare **Controllo produzione \> Ordini di produzione \> Tutti gli ordini di produzione** per aprire la pagina **Tutti gli ordini di produzione**.</span><span class="sxs-lookup"><span data-stu-id="98201-228">Select **Production control \> Production orders \> All production orders** to open the **All production orders** page.</span></span>
24. <span data-ttu-id="98201-229">Utilizzare il campo di filtro rapido per selezionare l'ordine di produzione a cui si sta lavorando.</span><span class="sxs-lookup"><span data-stu-id="98201-229">Use the quick filter field to select the production order that you've been working on.</span></span>
25. <span data-ttu-id="98201-230">Nel riquadro azioni, nella scheda **Magazzino** selezionare **Dettagli lavoro** per aprire la pagina **Lavoro**.</span><span class="sxs-lookup"><span data-stu-id="98201-230">On the Action Pane, on the **Warehouse** tab, select **Work details** to open the **Work** page.</span></span>

    <span data-ttu-id="98201-231">Notare che la pagina mostra due set di lavoro per il prelievo della materia prima.</span><span class="sxs-lookup"><span data-stu-id="98201-231">Notice that the page shows two sets of work for raw material picking.</span></span> <span data-ttu-id="98201-232">Il primo lavoro riguarda i materiali M8100 e M8101.</span><span class="sxs-lookup"><span data-stu-id="98201-232">The first work is for materials M8100 and M8101.</span></span> <span data-ttu-id="98201-233">Questi materiali vengono utilizzati nell'operazione 10.</span><span class="sxs-lookup"><span data-stu-id="98201-233">These materials are consumed by operation 10.</span></span> <span data-ttu-id="98201-234">Il secondo lavoro riguarda i materiali M8202 e M8250.</span><span class="sxs-lookup"><span data-stu-id="98201-234">The second work is for materials M8202 and M8250.</span></span> <span data-ttu-id="98201-235">Questi materiali vengono utilizzati dall'operazione 20, che corrisponde all'operazione in conto lavoro.</span><span class="sxs-lookup"><span data-stu-id="98201-235">These materials are consumed by operation 20, which is the subcontracted operation.</span></span>

    ![Due set di lavoro per il prelievo della materia prima nella pagina Lavoro.](./media/subcontract22_work-page.png)

26. <span data-ttu-id="98201-237">Avviare l'app del magazzino per elaborare il lavoro di magazzino per l'operazione 10.</span><span class="sxs-lookup"><span data-stu-id="98201-237">Start the warehousing app to process the warehouse work for operation 10.</span></span>

    <!-- TBD – screen shots for processing pick work for the materials. -->

27. <span data-ttu-id="98201-238">Selezionare **Controllo produzione \> Ordini di produzione \> Tutti gli ordini di produzione** per aprire la pagina **Tutti gli ordini di produzione**.</span><span class="sxs-lookup"><span data-stu-id="98201-238">Select **Production control \> Production orders \> All production orders** to open the **All production orders** page.</span></span>
28. <span data-ttu-id="98201-239">Utilizzare il campo di filtro rapido per selezionare l'ordine di produzione a cui si sta lavorando.</span><span class="sxs-lookup"><span data-stu-id="98201-239">Use the quick filter field to select the production order that you've been working on.</span></span>
29. <span data-ttu-id="98201-240">Nel riquadro azioni, nella scheda **Ordine di produzione** selezionare **Avvio** per aprire la finestra di dialogo **Avvio**.</span><span class="sxs-lookup"><span data-stu-id="98201-240">On the Action Pane, on the **Production order** tab, select **Start** to open the **Start** dialog box.</span></span>
30. <span data-ttu-id="98201-241">Nella scheda **Generale** specificare i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="98201-241">On the **General** tab, specify the following values:</span></span>

    - <span data-ttu-id="98201-242">Nel campo **Da oper. n.**</span><span class="sxs-lookup"><span data-stu-id="98201-242">In the **From Oper. No.**</span></span> <span data-ttu-id="98201-243">selezionare **10**.</span><span class="sxs-lookup"><span data-stu-id="98201-243">field, select **10**.</span></span>
    - <span data-ttu-id="98201-244">Nel campo **A oper. n.**</span><span class="sxs-lookup"><span data-stu-id="98201-244">In the **To Oper. No.**</span></span> <span data-ttu-id="98201-245">selezionare **10**.</span><span class="sxs-lookup"><span data-stu-id="98201-245">field, select **10**.</span></span>

    ![Valori impostati nella scheda Generale](./media/subcontract23_start-dialog.png)

31. <span data-ttu-id="98201-247">Selezionare **OK** per chiudere la finestra di dialogo **Avvio** e tornare alla pagina **Tutti gli ordini di produzione**.</span><span class="sxs-lookup"><span data-stu-id="98201-247">Select **OK** to close the **Start** dialog box and return to the **All production orders** page.</span></span>

    <span data-ttu-id="98201-248">Notare che lo stato dell'ordine di produzione è ora impostato su **Avviato**.</span><span class="sxs-lookup"><span data-stu-id="98201-248">Notice that the status of the production order is now **Started**.</span></span> <span data-ttu-id="98201-249">I materiali per l'operazione 10 vengono consumati da una registrazione automatica del giornale di registrazione distinte di prelievo.</span><span class="sxs-lookup"><span data-stu-id="98201-249">The materials for operation 10 are consumed by an automatic posting of the picking list journal.</span></span> <span data-ttu-id="98201-250">Il consumo di tempo per l'operazione 10 viene considerato da una registrazione automatica di un giornale di registrazione schede cicli di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="98201-250">Time consumption for operation 10 is accounted for by an automatic posting of a route card journal.</span></span>

32. <span data-ttu-id="98201-251">Avviare l'app del magazzino per elaborare il lavoro di magazzino per l'operazione 20.</span><span class="sxs-lookup"><span data-stu-id="98201-251">Start the warehousing app to process the warehouse work for operation 20.</span></span>

    <!-- TBD – screen shots for processing pick work for the materials. -->

33. <span data-ttu-id="98201-252">Nel riquadro azioni, nella scheda **Ordine di produzione** selezionare **Avvio** per aprire la finestra di dialogo **Avvio**.</span><span class="sxs-lookup"><span data-stu-id="98201-252">On the Action Pane, on the **Production order** tab, select **Start** to open the **Start** dialog box.</span></span>
34. <span data-ttu-id="98201-253">Nella scheda **Generale** specificare i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="98201-253">On the **General** tab, specify the following values:</span></span>

    - <span data-ttu-id="98201-254">Nel campo **Da oper. n.**</span><span class="sxs-lookup"><span data-stu-id="98201-254">In the **From Oper. No.**</span></span> <span data-ttu-id="98201-255">selezionare **20**.</span><span class="sxs-lookup"><span data-stu-id="98201-255">field, select **20**.</span></span>
    - <span data-ttu-id="98201-256">Nel campo **A oper. n.**</span><span class="sxs-lookup"><span data-stu-id="98201-256">In the **To Oper. No.**</span></span> <span data-ttu-id="98201-257">selezionare **20**.</span><span class="sxs-lookup"><span data-stu-id="98201-257">field, select **20**.</span></span>
    - <span data-ttu-id="98201-258">Nel campo **Quantità** immettere **10**.</span><span class="sxs-lookup"><span data-stu-id="98201-258">In the **Quantity** field, enter **10**.</span></span>
    - <span data-ttu-id="98201-259">Impostare l'opzione **Registra distinta di prelievo ora** su **No**.</span><span class="sxs-lookup"><span data-stu-id="98201-259">Set the **Post picking list now** option to **No**.</span></span>

    ![Valori impostati nella scheda Generale](./media/subcontract24_general-tab.png)

35. <span data-ttu-id="98201-261">Selezionare **OK** per chiudere la finestra di dialogo **Avvio** e tornare alla pagina **Tutti gli ordini di produzione**.</span><span class="sxs-lookup"><span data-stu-id="98201-261">Select **OK** to close the **Start** dialog box and return to the **All production orders** page.</span></span>

    <span data-ttu-id="98201-262">Verrà creata una distinta di prelievo per i materiali utilizzati per l'operazione di rivestimento e per l'articolo di tipo Assistenza.</span><span class="sxs-lookup"><span data-stu-id="98201-262">A picking list is created for the materials that are used for the Coating operation, and for the service item.</span></span> <span data-ttu-id="98201-263">L'articolo di tipo Assistenza rappresenta il costo dell'operazione in conto lavoro.</span><span class="sxs-lookup"><span data-stu-id="98201-263">The service item represents the cost of the subcontracted operation.</span></span>

36. <span data-ttu-id="98201-264">Nel riquadro azioni, nella scheda **Visualizza** scegliere **Distinta di prelievo** per aprire la pagina **Distinta di prelievo**.</span><span class="sxs-lookup"><span data-stu-id="98201-264">On the Action Pane, on the **View** tab, select **Picking list** to open the **Picking list** page.</span></span>
37. <span data-ttu-id="98201-265">Selezionare la distinta di prelievo che non è registrata e selezionare il numero del giornale di registrazione per visualizzare le righe del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="98201-265">Select the picking list that isn't posted, and then select the journal number to view the journal lines.</span></span>

    ![Righe del giornale di registrazione nella pagina Distinta di prelievo](./media/subcontract25_picking-list.png)

38. <span data-ttu-id="98201-267">Nel riquadro azioni, selezionare **Stampa** \> **Report distinte di prelievo** per aprire la finestra di dialogo **Report distinte di prelievo**.</span><span class="sxs-lookup"><span data-stu-id="98201-267">On the Action Pane, select **Print** \> **Picking list report** to open the **Picking list report** dialog box.</span></span>
39. <span data-ttu-id="98201-268">Impostare l'opzione **Utilizza layout bolla di consegna** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="98201-268">Set the **Use delivery note layout** option to **Yes**.</span></span>

    ![Finestra di dialogo Report distinte di prelievo](./media/subcontract26_picking-list-report-dialog.png)

40. <span data-ttu-id="98201-270">Selezionare **OK** per generare un report **Distinta di prelievo**.</span><span class="sxs-lookup"><span data-stu-id="98201-270">Select **OK** to generate a **Picking list** report.</span></span>

    <span data-ttu-id="98201-271">In questo caso viene stampata una bolla di consegna fornitore dal giornale di registrazione distinte di prelievo produzione.</span><span class="sxs-lookup"><span data-stu-id="98201-271">In this case, a vendor delivery note is printed from the production picking list journal.</span></span> <span data-ttu-id="98201-272">La bolla di consegna specifica i materiali che devono essere spediti al fornitore che si occupa dell'operazione di rivestimento.</span><span class="sxs-lookup"><span data-stu-id="98201-272">The delivery note specifies the materials that are shipped to the vendor who will do the Coating operation.</span></span>

    ![Report distinte di prelievo](./media/subcontract27_picking-list-report.png)

41. <span data-ttu-id="98201-274">Chiudere il report **Distinta di prelievo** per tornare alla pagina **Distinta di prelievo**.</span><span class="sxs-lookup"><span data-stu-id="98201-274">Close the **Picking list** report to return to the **Picking list** page.</span></span>
42. <span data-ttu-id="98201-275">Nel riquadro azioni, scegliere **Registra** per aprire la finestra di dialogo **Registra giornale**.</span><span class="sxs-lookup"><span data-stu-id="98201-275">On the Action Pane, select **Post** to open the **Post journal** dialog box.</span></span>

    ![Finestra di dialogo Registra giornale](./media/subcontract28_post-journal-dialog.png)

43. <span data-ttu-id="98201-277">Selezionare **OK** per chiudere la finestra di dialogo **Registra giornale**.</span><span class="sxs-lookup"><span data-stu-id="98201-277">Select **OK** to close the **Post journal** dialog box.</span></span>
44. <span data-ttu-id="98201-278">Aprire l'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="98201-278">Open the purchase order.</span></span>

    ![Pagina Ordine fornitore](./media/subcontract29_purchase-order-page.png)

45. <span data-ttu-id="98201-280">Nel riquadro azioni, nella scheda **Acquisti** selezionare **Conferma**.</span><span class="sxs-lookup"><span data-stu-id="98201-280">On the Action Pane, on the **Purchase** tab, select **Confirm**.</span></span>
46. <span data-ttu-id="98201-281">Selezionare **Registra** per aprire la finestra di dialogo **Registra giornale**.</span><span class="sxs-lookup"><span data-stu-id="98201-281">Select **Post** to open the **Post journal** dialog box.</span></span>
47. <span data-ttu-id="98201-282">Selezionare **OK** per chiudere la finestra di dialogo **Registra giornale** e tornare alla pagina **Ordine fornitore**.</span><span class="sxs-lookup"><span data-stu-id="98201-282">Select **OK** to close the **Post journal** dialog box and return to the **Purchase order** page.</span></span>
48. <span data-ttu-id="98201-283">Modificare il prezzo unitario da **33** a **40**.</span><span class="sxs-lookup"><span data-stu-id="98201-283">Change the unit price from **33** to **40**.</span></span>

    ![Prezzo unitario modificato nella pagina Ordine fornitore](./media/subcontract30_unit-price.png)

49. <span data-ttu-id="98201-285">Confermare di nuovo l'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="98201-285">Confirm the purchase order again.</span></span>
50. <span data-ttu-id="98201-286">Entrata prodotti.</span><span class="sxs-lookup"><span data-stu-id="98201-286">Product receipt.</span></span>

    ![Finestra di dialogo Registrazione entrata prodotti](./media/subcontract31_posting-product-receipt-dialog.png)

51. <span data-ttu-id="98201-288">Fattura acquisto.</span><span class="sxs-lookup"><span data-stu-id="98201-288">Purchase invoice.</span></span>
52. <span data-ttu-id="98201-289">Aggiornare lo stato di abbinamento.</span><span class="sxs-lookup"><span data-stu-id="98201-289">Update the match status.</span></span>

    ![Pagina Fattura fornitore](./media/subcontract32_vendor-invoice-page.png)

53. <span data-ttu-id="98201-291">Dichiarato finito.</span><span class="sxs-lookup"><span data-stu-id="98201-291">Report as finished.</span></span>

    ![Finestra di dialogo Dichiarazione di finito](./media/subcontract33_report-as-finished-dialog.png)

54. <span data-ttu-id="98201-293">Fine.</span><span class="sxs-lookup"><span data-stu-id="98201-293">End.</span></span>

    ![Finestra di dialogo Fine](./media/subcontract34_end-dialog.png)

55. <span data-ttu-id="98201-295">Confronto costi.</span><span class="sxs-lookup"><span data-stu-id="98201-295">Cost comparison.</span></span>

    ![Grafici di confronto costi](./media/subcontract35_cost-comparison-charts.png)

<span data-ttu-id="98201-297">Mancata impostazione nei dati.</span><span class="sxs-lookup"><span data-stu-id="98201-297">Missing setup in data.</span></span>
