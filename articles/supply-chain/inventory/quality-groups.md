---
title: Gruppi di controllo qualità articoli
description: In questo argomento viene descritto come utilizzare e creare gruppi di controllo qualità articoli per raggruppare logicamente i prodotti in modo che possano essere assegnati ad associazioni di controllo qualità per la generazione automatica di ordini di controllo qualità.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestQualityGroup, InventTestItemQualityGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3074a6a8cc054be045bf593b509e76a1043af0b7
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956710"
---
# <a name="item-quality-groups"></a><span data-ttu-id="c6c56-103">Gruppi di controllo qualità articoli</span><span class="sxs-lookup"><span data-stu-id="c6c56-103">Item quality groups</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c6c56-104">Un gruppo di controllo qualità rappresenta i requisiti di test comuni per gli articoli.</span><span class="sxs-lookup"><span data-stu-id="c6c56-104">A quality group represents common testing requirements for items.</span></span> <span data-ttu-id="c6c56-105">In questo argomento viene descritto come utilizzare e creare gruppi di controllo qualità articoli per raggruppare logicamente i prodotti in modo che possano essere assegnati ad associazioni di controllo qualità per la generazione automatica di ordini di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="c6c56-105">This topic describes how to use and create item quality groups to logically group products so that they can be assigned to quality associations for the automatic generation of quality orders.</span></span>

<span data-ttu-id="c6c56-106">Per impostare, modificare e visualizzare gli articoli assegnati a un gruppo di controllo qualità o i gruppi di controllo qualità assegnati a un articolo, vai a **Gestione articoli \> Impostazioni \> Gruppi di controllo qualità**.</span><span class="sxs-lookup"><span data-stu-id="c6c56-106">To set up, edit, and view the items that are assigned to a quality group, or the quality groups that are assigned to an item, go to **Inventory management \> Setup \> Quality groups**.</span></span> <span data-ttu-id="c6c56-107">Dopo la definizione dei requisiti di test nella pagine **Gruppi di test**, è possibile definire le regole per generare automaticamente gli ordini di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="c6c56-107">After you define the test requirements on the **Test groups** page, you can define the rules for automatically generating quality orders.</span></span> <span data-ttu-id="c6c56-108">Per semplificare il processo, non si definiscono le regole per i singoli articoli.</span><span class="sxs-lookup"><span data-stu-id="c6c56-108">To simplify the process, you don't define rules for individual items.</span></span> <span data-ttu-id="c6c56-109">Invece, puoi definire le regole per un gruppo di controllo qualità nella pagina **Associazioni di controllo qualità**.</span><span class="sxs-lookup"><span data-stu-id="c6c56-109">Instead, you can define the rules for a quality group on the **Quality associations** page.</span></span>

## <a name="example-of-an-item-quality-group"></a><span data-ttu-id="c6c56-110">Esempio di un gruppo di controllo qualità articoli</span><span class="sxs-lookup"><span data-stu-id="c6c56-110">Example of an item quality group</span></span>

<span data-ttu-id="c6c56-111">Una società di produzione acquista varie materie prime con gli stessi requisiti di test per quanto riguarda l'ispezione in entrata.</span><span class="sxs-lookup"><span data-stu-id="c6c56-111">A manufacturing company purchases various raw materials that have the same testing requirements for incoming inspection.</span></span> <span data-ttu-id="c6c56-112">Pertanto, la società definisce un gruppo di controllo qualità e vi assegna i numeri articolo associati alle materie prime.</span><span class="sxs-lookup"><span data-stu-id="c6c56-112">Therefore, the company defines a quality group and then assigns the item numbers that are associated with the raw materials to that group.</span></span> <span data-ttu-id="c6c56-113">In seguito, la società acquista un nuovo tipo di materie prima con gli stessi requisiti di test.</span><span class="sxs-lookup"><span data-stu-id="c6c56-113">Later, the company purchases a new type of raw material that has the same testing requirements.</span></span> <span data-ttu-id="c6c56-114">Invece di impostare nuovi requisiti di test per il nuovo materiale, la società aggiunge il relativo numero articolo al gruppo di controllo qualità esistente.</span><span class="sxs-lookup"><span data-stu-id="c6c56-114">Instead of setting up new testing requirements for the new material, the company adds the item number for the new material to the existing quality group.</span></span>

<span data-ttu-id="c6c56-115">La stessa società produce inoltre articoli con gli stessi requisiti di test della produzione e spedisce articoli con gli stessi requisiti per quanto riguarda l'esecuzione di test prima della spedizione.</span><span class="sxs-lookup"><span data-stu-id="c6c56-115">The same company also produces items that have the same production testing requirements and ships items that have the same requirement for pre-shipment testing.</span></span> <span data-ttu-id="c6c56-116">Pertanto, la società definisce due ulteriori gruppi di controllo qualità e assegna a ognuno i numeri di articolo rilevanti.</span><span class="sxs-lookup"><span data-stu-id="c6c56-116">Therefore, the company defines two additional quality groups and then assigns the relevant item numbers to each group.</span></span>

## <a name="create-a-quality-group"></a><span data-ttu-id="c6c56-117">Creare un gruppo di controllo qualità</span><span class="sxs-lookup"><span data-stu-id="c6c56-117">Create a quality group</span></span>

<span data-ttu-id="c6c56-118">Per creare un gruppo di controllo qualità, eseguire i passaggi indicati di seguito:</span><span class="sxs-lookup"><span data-stu-id="c6c56-118">To create a quality group, follow these steps.</span></span>

1. <span data-ttu-id="c6c56-119">Andare a **Gestione articoli \> Impostazioni \> Controllo qualità \> Gruppi di controllo qualità**.</span><span class="sxs-lookup"><span data-stu-id="c6c56-119">Go to **Inventory management \> Setup \> Quality control \> Quality groups**.</span></span>
1. <span data-ttu-id="c6c56-120">Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="c6c56-120">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="c6c56-121">Quindi imposta i seguenti campi per la nuova riga:</span><span class="sxs-lookup"><span data-stu-id="c6c56-121">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="c6c56-122">**Gruppo di controllo qualità** – Immetti un ID o nome univoco per il gruppo di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="c6c56-122">**Quality group** – Enter a unique ID or name for the quality group.</span></span>
    - <span data-ttu-id="c6c56-123">**Descrizione** - Immettere una descrizione dettagliata del gruppo di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="c6c56-123">**Description** – Enter a detailed description of the quality group.</span></span>

1. <span data-ttu-id="c6c56-124">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c6c56-124">Close the page.</span></span>

## <a name="manually-add-items-to-a-quality-group"></a><span data-ttu-id="c6c56-125">Aggiungere manualmente articoli a gruppo di controllo qualità</span><span class="sxs-lookup"><span data-stu-id="c6c56-125">Manually add items to a quality group</span></span>

<span data-ttu-id="c6c56-126">Per aggiungere manualmente articoli a un gruppo di controllo qualità, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="c6c56-126">To manually add items to a quality group, follow these steps.</span></span>

1. <span data-ttu-id="c6c56-127">Andare a **Gestione articoli \> Impostazioni \> Controllo qualità \> Gruppi di controllo qualità**.</span><span class="sxs-lookup"><span data-stu-id="c6c56-127">Go to **Inventory management \> Setup \> Quality control \> Quality groups**.</span></span>
1. <span data-ttu-id="c6c56-128">Seleziona il gruppo di controllo qualità a cui desideri aggiungere gli articoli.</span><span class="sxs-lookup"><span data-stu-id="c6c56-128">Select the quality group that you want to add items to.</span></span>
1. <span data-ttu-id="c6c56-129">Nel riquadro azioni seleziona **Articoli**.</span><span class="sxs-lookup"><span data-stu-id="c6c56-129">On the Action Pane, select **Items**.</span></span>
1. <span data-ttu-id="c6c56-130">Nella pagina **Articoli in gruppi di controllo qualità**, nel riquadro azioni selezionare **Nuovo** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="c6c56-130">On the **Items in quality groups** page, on the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="c6c56-131">Quindi, per la nuova riga, imposta il campo **Numero articolo** sul numero di articolo che si desidera aggiungere.</span><span class="sxs-lookup"><span data-stu-id="c6c56-131">Then, for the new row, set the **Item number** field to the item number that you want to add.</span></span>
1. <span data-ttu-id="c6c56-132">Ripeti il passaggio precedente per ogni articolo aggiuntivo che devi aggiungere.</span><span class="sxs-lookup"><span data-stu-id="c6c56-132">Repeat the previous step for each additional item that must be added.</span></span>
1. <span data-ttu-id="c6c56-133">Chiudere le pagine.</span><span class="sxs-lookup"><span data-stu-id="c6c56-133">Close the pages.</span></span>

## <a name="add-multiple-items-to-a-quality-group"></a><span data-ttu-id="c6c56-134">Aggiungere più articoli a gruppo di controllo qualità</span><span class="sxs-lookup"><span data-stu-id="c6c56-134">Add multiple items to a quality group</span></span>

<span data-ttu-id="c6c56-135">Per aggiungere più articoli a un gruppo di controllo qualità, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="c6c56-135">To add multiple items to a quality group, follow these steps.</span></span>

1. <span data-ttu-id="c6c56-136">Andare a **Gestione articoli \> Impostazioni \> Controllo qualità \> Gruppi di controllo qualità**.</span><span class="sxs-lookup"><span data-stu-id="c6c56-136">Go to **Inventory management \> Setup \> Quality control \> Quality groups**.</span></span>
1. <span data-ttu-id="c6c56-137">Crea o seleziona il gruppo di controllo qualità a cui desideri aggiungere gli articoli.</span><span class="sxs-lookup"><span data-stu-id="c6c56-137">Create or select the quality group that you want to add items to.</span></span>
1. <span data-ttu-id="c6c56-138">Nel riquadro azioni seleziona **Aggiungi articoli**.</span><span class="sxs-lookup"><span data-stu-id="c6c56-138">On the Action Pane, select **Add items**.</span></span>
1. <span data-ttu-id="c6c56-139">Nella finestra di dialogo **Richiesta di informazioni**, immettere i criteri di filtro per gli articoli che si desidera aggiungere.</span><span class="sxs-lookup"><span data-stu-id="c6c56-139">In the **Inquiry** dialog box, enter the filter criteria for the items that you want to add.</span></span> <span data-ttu-id="c6c56-140">Ad esempio, potresti filtrare tutti gli articoli in un gruppo di articoli specifico.</span><span class="sxs-lookup"><span data-stu-id="c6c56-140">For example, you might filter for all items in a specific item group.</span></span>
1. <span data-ttu-id="c6c56-141">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6c56-141">Select **OK**.</span></span>
1. <span data-ttu-id="c6c56-142">Nella finestra di dialogo **Aggiungi articoli**, una griglia mostra tutti gli elementi che corrispondono alla tua query.</span><span class="sxs-lookup"><span data-stu-id="c6c56-142">In the **Add items** dialog box, a grid shows all the items that match your query.</span></span> <span data-ttu-id="c6c56-143">Rivedi i risultati.</span><span class="sxs-lookup"><span data-stu-id="c6c56-143">Review the results.</span></span>

    <span data-ttu-id="c6c56-144">Se sono necessarie modifiche, selezionare **Seleziona** per tornare alla finestra di dialogo **Richiesta di informazioni** e modificare la query.</span><span class="sxs-lookup"><span data-stu-id="c6c56-144">If any changes are required, select **Select** to return to the **Inquiry** dialog box, and adjust your query.</span></span>

1. <span data-ttu-id="c6c56-145">Quando i risultati includono tutti gli articoli che desideri aggiungere, seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6c56-145">When the results include all the items that you want to add, select **OK**.</span></span>
1. <span data-ttu-id="c6c56-146">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c6c56-146">Close the page.</span></span>

## <a name="manually-associate-an-item-with-a-quality-group"></a><span data-ttu-id="c6c56-147">Associare manualmente un articolo a un gruppo di controllo qualità</span><span class="sxs-lookup"><span data-stu-id="c6c56-147">Manually associate an item with a quality group</span></span>

<span data-ttu-id="c6c56-148">Per associare manualmente un articolo a un gruppo di controllo qualità, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="c6c56-148">To manually associate an item with a quality group, follow these steps.</span></span>

1. <span data-ttu-id="c6c56-149">Andare a **Gestione articoli \> Impostazioni \> Controllo qualità \> Gruppi di controllo qualità articoli**.</span><span class="sxs-lookup"><span data-stu-id="c6c56-149">Go to **Inventory management \> Setup \> Quality control \> Item quality groups**.</span></span>
1. <span data-ttu-id="c6c56-150">Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="c6c56-150">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="c6c56-151">Quindi imposta i seguenti campi per la nuova riga:</span><span class="sxs-lookup"><span data-stu-id="c6c56-151">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="c6c56-152">**Numero articolo** - Seleziona il numero dell'articolo da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="c6c56-152">**Item number** – Select the item number to add.</span></span>
    - <span data-ttu-id="c6c56-153">**Gruppo di controllo qualità** - Seleziona il gruppo di controllo qualità da assegnare all'articolo.</span><span class="sxs-lookup"><span data-stu-id="c6c56-153">**Quality group** – Select the quality group to assign to the item.</span></span>

1. <span data-ttu-id="c6c56-154">Ripetere il passaggio precedente per ogni combinazione aggiuntiva di un articolo e un gruppo di controllo qualità che deve essere aggiunto.</span><span class="sxs-lookup"><span data-stu-id="c6c56-154">Repeat the previous step for each additional combination of an item and a quality group that must be added.</span></span>
1. <span data-ttu-id="c6c56-155">Chiudere le pagine.</span><span class="sxs-lookup"><span data-stu-id="c6c56-155">Close the pages.</span></span>

## <a name="manually-add-a-quality-group-from-the-released-products-page"></a><span data-ttu-id="c6c56-156">Aggiungere manualmente un gruppo di controllo qualità dalla pagina Prodotti rilasciati</span><span class="sxs-lookup"><span data-stu-id="c6c56-156">Manually add a quality group from the Released products page</span></span>

<span data-ttu-id="c6c56-157">Per aggiungere manualmente un gruppo di controllo qualità dalla pagina **Prodotti rilasciati**, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="c6c56-157">To manually add a quality group from the **Released products** page, follow these steps.</span></span>

1. <span data-ttu-id="c6c56-158">Fare clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="c6c56-158">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="c6c56-159">Selezionare il prodotto a cui si desidera assegnare un gruppo di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="c6c56-159">Select the product that you want to assign a quality group to.</span></span>
1. <span data-ttu-id="c6c56-160">Nel riquadro azioni, nella scheda **Gestione articoli**, nel gruppo **Qualità**, selezionare **Gruppi di controllo qualità articoli**.</span><span class="sxs-lookup"><span data-stu-id="c6c56-160">On the Action Pane, on the **Manage inventory** tab, in the **Quality** group, select **Item quality groups**.</span></span>
1. <span data-ttu-id="c6c56-161">Nella pagina **Articoli in gruppi di controllo qualità**, nel riquadro azioni selezionare **Nuovo** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="c6c56-161">On the **Items in quality groups** page, on the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="c6c56-162">Quindi, per la nuova riga, imposta il campo **Gruppo di controllo qualità** sul gruppo di controllo qualità che si desidera assegnare al prodotto.</span><span class="sxs-lookup"><span data-stu-id="c6c56-162">Then, for the new row, set the **Quality group** field to the quality group that you want to assign to the product.</span></span>
1. <span data-ttu-id="c6c56-163">Ripetere il passaggio precedente per ogni gruppo di controllo qualità aggiuntivo che si desidera assegnare al prodotto.</span><span class="sxs-lookup"><span data-stu-id="c6c56-163">Repeat the previous step for each additional quality group that you want to assign to the product.</span></span>
1. <span data-ttu-id="c6c56-164">Chiudere le pagine.</span><span class="sxs-lookup"><span data-stu-id="c6c56-164">Close the pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c6c56-165">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="c6c56-165">Additional resources</span></span>

- [<span data-ttu-id="c6c56-166">Strumenti di test di gestione qualità</span><span class="sxs-lookup"><span data-stu-id="c6c56-166">Quality management test instruments</span></span>](quality-test-instruments.md)
- [<span data-ttu-id="c6c56-167">Test di gestione qualità</span><span class="sxs-lookup"><span data-stu-id="c6c56-167">Quality management tests</span></span>](quality-tests.md)
- [<span data-ttu-id="c6c56-168">Gruppi di test di gestione qualità</span><span class="sxs-lookup"><span data-stu-id="c6c56-168">Quality management test groups</span></span>](quality-test-groups.md)
- [<span data-ttu-id="c6c56-169">Variabili di test di gestione qualità</span><span class="sxs-lookup"><span data-stu-id="c6c56-169">Quality management test variables</span></span>](quality-test-variables.md)
- [<span data-ttu-id="c6c56-170">Associazioni di controllo qualità</span><span class="sxs-lookup"><span data-stu-id="c6c56-170">Quality associations</span></span>](quality-associations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
