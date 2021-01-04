---
title: Previsioni di manutenzione
description: In questo argomento vengono descritte le previsioni di manutenzione in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderForecastToJournals, EntAssetWorkOrderForecast
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2686dd6db032239e2a3aac03f3998cee055302f6
ms.sourcegitcommit: 5f21cfde36c43887ec209bba4a12b830a1746fcf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2020
ms.locfileid: "4431598"
---
# <a name="maintenance-forecasts"></a><span data-ttu-id="39452-103">Previsioni di manutenzione</span><span class="sxs-lookup"><span data-stu-id="39452-103">Maintenance forecasts</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="39452-104">Quando si crea un ordine di lavoro, si creano processi di ordine di lavoro con i relativi cespiti e tipi di processo di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="39452-104">When you create a work order, you create work order jobs that have related assets and maintenance job types.</span></span> <span data-ttu-id="39452-105">Quando si seleziona un tipo di processo di manutenzione contenente previsioni di manutenzione, queste vengono copiate automaticamente nell'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="39452-105">When you select a maintenance job type that contains maintenance forecasts, the forecasts are automatically copied to the work order.</span></span>

<span data-ttu-id="39452-106">È possibile aggiungere righe di previsione a un ordine di lavoro o cancellarle da un ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="39452-106">You might be able to add forecast lines to a work order or delete them from a work order.</span></span> <span data-ttu-id="39452-107">L'impostazione dello stato del ciclo di vita dell'ordine di lavoro, il tipo di progetto correlato e le regole della fase correlate al tipo di progetto determinano se è possibile aggiungere o modificare le righe di previsione.</span><span class="sxs-lookup"><span data-stu-id="39452-107">The setup of the work order lifecycle state, the related project type, and the stage rules that are related to the project type determine whether you can add or edit forecast lines.</span></span> <span data-ttu-id="39452-108">Per ulteriori informazioni sugli stati del ciclo di vita di ordine di lavoro e sulle fasi di progetto correlate, vedere [Previsioni, ordini di lavoro e progetti](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="39452-108">For more information about work order lifecycle states and related project stages, see [Forecasts, work orders, and projects](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).</span></span>

1. <span data-ttu-id="39452-109">Selezionare **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.</span><span class="sxs-lookup"><span data-stu-id="39452-109">Select **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="39452-110">Selezionare l'ordine di lavoro nell'elenco, quindi nel riquadro azioni > nella scheda **Ordine di lavoro** > nel gruppo **Progetto**, selezionare **Previsione**.</span><span class="sxs-lookup"><span data-stu-id="39452-110">Select the work order in the list, and then, on the Action Pane > **Work order** tab > the **Project** group, select **Forecast**.</span></span> <span data-ttu-id="39452-111">Nella pagina **Previsione di manutenzione ordine di lavoro** vengono visualizzate le righe di previsione del tipo di processo di manutenzione selezionato nel processo di ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="39452-111">The **Work order maintenance forecast** page shows forecast lines from the maintenance job type that is selected on the work order job.</span></span>


## <a name="add-an-hours-forecast-to-a-work-order"></a><span data-ttu-id="39452-112">Aggiungere una previsione di ore a un ordine di lavoro</span><span class="sxs-lookup"><span data-stu-id="39452-112">Add an hours forecast to a work order</span></span>

1. <span data-ttu-id="39452-113">Nella pagina **Previsioni di manutenzione dell'ordine di lavoro**, selezionare il processo ordine di lavoro a cui aggiungere una previsione.</span><span class="sxs-lookup"><span data-stu-id="39452-113">On the **Work order maintenance forecast** page, select the work order job to add a forecast to.</span></span>

2. <span data-ttu-id="39452-114">Nella Scheda dettaglio **Ore** selezionare **Aggiungi** per creare una nuova riga.</span><span class="sxs-lookup"><span data-stu-id="39452-114">On the **Hours** FastTab, select **Add** to create a new line.</span></span>

3. <span data-ttu-id="39452-115">Selezionare una categoria nel campo **Categoria**.</span><span class="sxs-lookup"><span data-stu-id="39452-115">In the **Category** field, select a category.</span></span>

4. <span data-ttu-id="39452-116">Immettere il numero di ore previste nel campo **Ore**.</span><span class="sxs-lookup"><span data-stu-id="39452-116">In the **Hours** field, enter the number of forecasted hours.</span></span>

5. <span data-ttu-id="39452-117">Nel campo **Proprietà riga**, selezionare il tipo di spese da utilizzare nella riga.</span><span class="sxs-lookup"><span data-stu-id="39452-117">In the **Line property** field, select the type of charge that should be used on the line.</span></span>


## <a name="add-an-items-forecast-to-a-work-order"></a><span data-ttu-id="39452-118">Aggiungere una previsione di articoli a un ordine di lavoro</span><span class="sxs-lookup"><span data-stu-id="39452-118">Add an items forecast to a work order</span></span>

<span data-ttu-id="39452-119">Sono disponibili tre modi per aggiungere articoli a una previsione di manutenzione di ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="39452-119">There are three ways to add items to a work order maintenance forecast.</span></span> <span data-ttu-id="39452-120">È possibile righe per articoli (pezzi di ricambio) che non sono inclusi nell'elenco dei pezzi di ricambio o nel DBA cespiti, selezionare i pezzi di ricambio dall'elenco dei pezzi di ricambio approvato e selezionare articoli nel DBA cespiti.</span><span class="sxs-lookup"><span data-stu-id="39452-120">You can create lines for items (spare parts) that aren't included on the spare parts list or the asset bill of materials (BOM), you can select spare parts from the approved spare parts list, or you can select items from the asset BOM.</span></span>

- <span data-ttu-id="39452-121">Nella pagina **Previsioni di manutenzione dell'ordine di lavoro**, selezionare il processo ordine di lavoro a cui aggiungere una previsione.</span><span class="sxs-lookup"><span data-stu-id="39452-121">On the **Work order maintenance forecast** page, select the work order job to add a forecast to.</span></span>

- <span data-ttu-id="39452-122">Nella scheda dettaglio **Articoli**, aggiungere gli articoli alla previsione di manutenzione utilizzando il metodo appropriato.</span><span class="sxs-lookup"><span data-stu-id="39452-122">On the **Items** FastTab, add items to the maintenance forecast by using the appropriate method.</span></span>

<span data-ttu-id="39452-123">Per creare una riga per un pezzo di ricambio non incluso nell'elenco dei pezzi di ricambio o nel DBA cespiti, effettuare i seguenti passaggi:</span><span class="sxs-lookup"><span data-stu-id="39452-123">To create a line for a spare part that isn't on the spare parts list or the asset BOM, follow these steps:</span></span>

1. <span data-ttu-id="39452-124">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="39452-124">Select **Add**.</span></span>
2. <span data-ttu-id="39452-125">Nel campo **Numero articolo**, selezionare l'articolo.</span><span class="sxs-lookup"><span data-stu-id="39452-125">In the **Item number** field, select the item.</span></span>
3. <span data-ttu-id="39452-126">Nel campo **Quantità di vendita** immettere la quantità.</span><span class="sxs-lookup"><span data-stu-id="39452-126">In the **Sales quantity** field, enter the quantity.</span></span>
4. <span data-ttu-id="39452-127">Nel campo **Unità** selezionare l'unità di misura per la quantità.</span><span class="sxs-lookup"><span data-stu-id="39452-127">In the **Unit** field, select the unit of measure for the quantity.</span></span>
5. <span data-ttu-id="39452-128">Nei campi **Prezzo di costo** e **Valuta** immettere i valori appropriati.</span><span class="sxs-lookup"><span data-stu-id="39452-128">In the **Cost price** and **Currency** fields, enter appropriate values.</span></span>
6. <span data-ttu-id="39452-129">Nel campo **Proprietà riga**, selezionare una proprietà riga.</span><span class="sxs-lookup"><span data-stu-id="39452-129">In the **Line property** field, select a line property.</span></span>
7. <span data-ttu-id="39452-130">Per modificare l'elenco delle dimensioni visualizzate nelle righe degli articoli, selezionare **Inventario** > **Visualizza dimensioni**, selezionare le dimensioni e impostare l'opzione **Salva impostazione** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="39452-130">To change the list of dimensions that is shown on the item lines, select **Inventory** > **Display dimensions**, select the dimensions, and then set the **Save setup** option to **Yes**.</span></span>

<span data-ttu-id="39452-131">Per aggiungere un pezzo di ricambio da un elenco di pezzi di ricambio approvato, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="39452-131">To add a spare part from an approved spare parts list, follow these steps:</span></span>

1. <span data-ttu-id="39452-132">Selezionare **Aggiungi pezzi di ricambio**.</span><span class="sxs-lookup"><span data-stu-id="39452-132">Select **Add spare parts**.</span></span>
2. <span data-ttu-id="39452-133">Selezionare il pezzo di ricambio e modificare le informazioni secondo le necessità.</span><span class="sxs-lookup"><span data-stu-id="39452-133">Select the spare part, and edit the related information as you require.</span></span>
3. <span data-ttu-id="39452-134">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="39452-134">Select **OK**.</span></span>

<span data-ttu-id="39452-135">Per aggiungere un articolo dal DBA cespiti, effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="39452-135">To add an item from the asset BOM, follow these steps:</span></span>

1. <span data-ttu-id="39452-136">Selezionare **Aggiungi articoli DBA**.</span><span class="sxs-lookup"><span data-stu-id="39452-136">Select **Add BOM items**.</span></span>
2. <span data-ttu-id="39452-137">Selezionare l'articolo e modificare le informazioni secondo le necessità.</span><span class="sxs-lookup"><span data-stu-id="39452-137">Select the item, and edit the related information as you require.</span></span>
3. <span data-ttu-id="39452-138">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="39452-138">Select **OK**.</span></span>

<span data-ttu-id="39452-139">Per ottenere una panoramica di dove l'articolo viene utilizzato nella riga selezionata in relazione ai cespiti, ai valori predefiniti di tipo di processo di manutenzione, pezzi di ricambio e ordini di lavoro, selezionare **Utilizzo dell'articolo**.</span><span class="sxs-lookup"><span data-stu-id="39452-139">To get an overview that shows where the item on the selected line is used in relation to assets, maintenance job type defaults, spare parts, and work orders in Asset Management, select **Item where used**.</span></span> <span data-ttu-id="39452-140">Per ulteriori informazioni su questa panoramica, vedere [Utilizzo dell'articolo](../controlling-and-reporting/item-where-used.md).</span><span class="sxs-lookup"><span data-stu-id="39452-140">For more information about this overview, see [Item where used](../controlling-and-reporting/item-where-used.md).</span></span>


## <a name="add-an-expense-forecast-to-a-work-order"></a><span data-ttu-id="39452-141">Aggiungere una previsione di spesa a un ordine di lavoro</span><span class="sxs-lookup"><span data-stu-id="39452-141">Add an expense forecast to a work order</span></span>

1. <span data-ttu-id="39452-142">Nella pagina **Previsioni di manutenzione dell'ordine di lavoro**, selezionare il processo ordine di lavoro a cui aggiungere una previsione.</span><span class="sxs-lookup"><span data-stu-id="39452-142">On the **Work order maintenance forecast** page, select the work order job to add a forecast to.</span></span>

2. <span data-ttu-id="39452-143">Nella Scheda dettaglio **Spesa** selezionare **Aggiungi** per creare una riga.</span><span class="sxs-lookup"><span data-stu-id="39452-143">On the **Expense** FastTab, select **Add** to create a line.</span></span>

3. <span data-ttu-id="39452-144">Selezionare una categoria nel campo **Categoria**.</span><span class="sxs-lookup"><span data-stu-id="39452-144">In the **Category** field, select a category.</span></span>

4. <span data-ttu-id="39452-145">Nel campo **Quantità** immettere la quantità.</span><span class="sxs-lookup"><span data-stu-id="39452-145">In the **Quantity** field, enter the quantity.</span></span>

5. <span data-ttu-id="39452-146">Nei campi **Prezzo di costo**, **Valuta di vendita** e **Prezzo di vendita**, immettere i valori appropriati.</span><span class="sxs-lookup"><span data-stu-id="39452-146">In the **Cost price**, **Sales currency**, and **Sales price** fields, enter appropriate values.</span></span>

6. <span data-ttu-id="39452-147">Nel campo **Proprietà riga**, selezionare il tipo di spese da utilizzare nella riga.</span><span class="sxs-lookup"><span data-stu-id="39452-147">In the **Line property** field, select the type of charge that should be used on the line.</span></span>

>[!NOTE]
><span data-ttu-id="39452-148">La Scheda dettaglio **Totali previsione di manutenzione** mostra una panoramica del numero di righe create per il processo di ordine di lavoro selezionato e per l'ordine di lavoro in ogni scheda dettaglio.</span><span class="sxs-lookup"><span data-stu-id="39452-148">The **Maintenance forecast totals** FastTab shows an overview of the number of lines that have been created, for the selected work order job and for the work order, on each FastTab.</span></span> <span data-ttu-id="39452-149">Mostra inoltre il totale delle ore lavorative previste per l'ordine di lavoro e il processo di ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="39452-149">It also shows the total forecasted work hours for the work order job and the work order.</span></span>

<span data-ttu-id="39452-150">Nell'illustrazione seguente è illustrato un esempio della pagina **Previsioni di manutenzione dell'ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="39452-150">The illustration below shows an example of the **Work order maintenance forecast** page.</span></span>

![Figura 1](media/06-work-orders.png)


## <a name="automatic-update-of-work-order-forecasts"></a><span data-ttu-id="39452-152">Aggiornamento automatico delle previsioni dell'ordine di lavoro</span><span class="sxs-lookup"><span data-stu-id="39452-152">Automatic update of work order forecasts</span></span>

<span data-ttu-id="39452-153">Se i costi delle ore, i costi degli articoli e le spese vengono aggiornati in altri moduli in Microsoft Dynamics 365 for Finance and Operations, le previsioni sugli ordini di lavoro in Gestione cespiti possono essere aggiornate automaticamente per riflettere tali modifiche.</span><span class="sxs-lookup"><span data-stu-id="39452-153">If hour costs, item costs, and expenses are updated in other modules in Microsoft Dynamics 365 for Finance and Operations, work order forecasts in Asset Management can automatically be updated to reflect those changes.</span></span> <span data-ttu-id="39452-154">Questa funzionalità garantisce l'utilizzo degli ultimi prezzi di costo nelle previsioni dell'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="39452-154">This capability helps guarantee that the latest cost prices are always used in your work order forecasts.</span></span> <span data-ttu-id="39452-155">È inoltre possibile apportare aggiornamenti simili per le [previsioni del tipo di processo di manutenzione](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).</span><span class="sxs-lookup"><span data-stu-id="39452-155">You can also do similar updates for [maintenance job type forecasts](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).</span></span>

1. <span data-ttu-id="39452-156">Selezionare **Gestione cespiti** > **Periodico** > **Previsione** > **Aggiorna previsione ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="39452-156">Select **Asset management** > **Periodic** > **Forecast** > **Update work order forecast**.</span></span>

2. <span data-ttu-id="39452-157">Nella finestra di dialogo **Aggiorna previsione ordine di lavoro**, nella scheda dettaglio **Record da includere**, è possibile aggiungere selezioni relative a specifici ordini di lavoro o processi di ordine di lavoro secondo le necessità.</span><span class="sxs-lookup"><span data-stu-id="39452-157">In the **Update work order forecast** dialog, on the **Records to include** FastTab, you can add selections regarding specific work orders or work order jobs, as you require.</span></span> <span data-ttu-id="39452-158">Fare clic su **Filtro** per effettuare la selezione delle opzioni rilevanti.</span><span class="sxs-lookup"><span data-stu-id="39452-158">Click **Filter** to make the relevant selections.</span></span>

3. <span data-ttu-id="39452-159">Nella Scheda dettaglio **Esecuzione in background**, è possibile impostare l'aggiornamento automatico come processo batch, come necessario.</span><span class="sxs-lookup"><span data-stu-id="39452-159">On the **Run in the background** FastTab, you can set up the automatic update as a batch job, as you require.</span></span>

4. <span data-ttu-id="39452-160">Selezionare **OK** per avviare l'aggiornamento delle previsioni.</span><span class="sxs-lookup"><span data-stu-id="39452-160">Select **OK** to start the forecast update.</span></span>


<span data-ttu-id="39452-161">Nella figura seguente è illustrato un esempio della finestra di dialogo **Aggiorna previsione ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="39452-161">The illustration below shows an example of the **Update work order forecast** dialog.</span></span>

![Figura 2](media/07-work-orders.png)
