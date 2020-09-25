---
title: Report per confrontare i prezzi degli articoli in magazzino
description: Informazioni su come generare un report per confrontare i prezzi degli articoli in magazzino e quindi sfogliare e/o esportare il risultato.
author: AndersGirke
manager: tfehr
ms.date: 01/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace, InventItemPriceCompareStorage, InventItemPriceCompareStorageDetailsChart, InventItemPriceCompareStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2020-03-01
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 73e43a685f390fd718028de6add0370dfcd6cf3b
ms.sourcegitcommit: cd339f48066b1d0fc740b513cb72ea19015acd16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "3759642"
---
# <a name="compare-item-prices-storage-report"></a><span data-ttu-id="6875d-103">Report per confrontare i prezzi degli articoli in magazzino</span><span class="sxs-lookup"><span data-stu-id="6875d-103">Compare item prices storage report</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6875d-104">Questo argomento spiega come eseguire a report per **confrontare i prezzi degli articoli in magazzino** e rendere disponibile l'output in formato digitale, sia come pagina interattiva in Dynamics 365 Supply Chain Management o come documento esportato in uno dei diversi formati.</span><span class="sxs-lookup"><span data-stu-id="6875d-104">This topic explains how to run a **Compare item prices storage** report and make the output available digitally, either as an interactive page in Dynamics 365 Supply Chain Management, or as an exported document in any of several formats.</span></span>

<span data-ttu-id="6875d-105">Quando si visualizza il report in un browser, le colonne e i saldi aggregati vengono modificati in modo dinamico, a seconda del layout configurato.</span><span class="sxs-lookup"><span data-stu-id="6875d-105">When you view the report in your browser, columns and aggregate balances are dynamically adjusted, depending on your configured layout.</span></span> <span data-ttu-id="6875d-106">È possibile ordinare i risultati, filtrarli, approfondire i dati e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="6875d-106">You can sort the results, filter them, drill down into the data, and more.</span></span>

<span data-ttu-id="6875d-107">I risultati del report sono memorizzati nell'entità dati **Confronta prezzi articoli**, che consente di filtrare ed esportare i risultati in un formato come CSV o Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="6875d-107">Report results are stored in the **Compare item prices** data entity, which lets you filter and export the results to a format such as CSV or Microsoft Excel.</span></span>

<span data-ttu-id="6875d-108">Il report per **confrontare i prezzi degli articoli in magazzino** è utile nei casi in cui l'output contiene molte righe.</span><span class="sxs-lookup"><span data-stu-id="6875d-108">The **Compare item prices storage** report is helpful in cases where the output contains many lines.</span></span> <span data-ttu-id="6875d-109">Ad esempio, l'output conterrà molte righe se nella versione di determinazione costi sono presenti più di 40.000 articoli con un prezzo in sospeso.</span><span class="sxs-lookup"><span data-stu-id="6875d-109">For example, the output will contain many lines if you have more than 40,000 items holding a pending item price in the costing version.</span></span>

## <a name="enable-compare-item-prices-storage"></a><span data-ttu-id="6875d-110">Abilitare il confronto dei prezzi degli articoli in magazzino</span><span class="sxs-lookup"><span data-stu-id="6875d-110">Enable compare item prices storage</span></span>

<span data-ttu-id="6875d-111">Prima di utilizzare questa funzionalità, è necessario abilitarla nel sistema.</span><span class="sxs-lookup"><span data-stu-id="6875d-111">Before you can use this feature, you must enable it on your system.</span></span> <span data-ttu-id="6875d-112">Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla se necessario.</span><span class="sxs-lookup"><span data-stu-id="6875d-112">Administrators can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the feature status and enable it if needed.</span></span> <span data-ttu-id="6875d-113">La funzione viene elencata come:</span><span class="sxs-lookup"><span data-stu-id="6875d-113">Here, the feature is listed as:</span></span>

- <span data-ttu-id="6875d-114">**Modulo** - Gestione costi</span><span class="sxs-lookup"><span data-stu-id="6875d-114">**Module** - Cost management</span></span>
- <span data-ttu-id="6875d-115">**Nome della funzione** - Confronto dei prezzi degli articoli in magazzino</span><span class="sxs-lookup"><span data-stu-id="6875d-115">**Feature name** - Compare item price storage</span></span>

## <a name="generate-a-compare-item-prices-storage-report"></a><span data-ttu-id="6875d-116">Generare un report in cui vengono confrontati i prezzi degli articoli in magazzino</span><span class="sxs-lookup"><span data-stu-id="6875d-116">Generate a Compare item prices storage report</span></span>

<span data-ttu-id="6875d-117">Seguire questi passaggi per generare e archiviare un report per **confrontare i prezzi degli articoli in magazzino**:</span><span class="sxs-lookup"><span data-stu-id="6875d-117">Follow these steps to generate and store a **Compare item prices storage** report:</span></span>

1. <span data-ttu-id="6875d-118">Andare a **Gestione costi > Richieste di informazioni e report > Report costi predeterminati > Confronta prezzi degli articoli in magazzino**.</span><span class="sxs-lookup"><span data-stu-id="6875d-118">Go to **Cost management > Inquiries and reports > Predetermined cost reports > Compare item prices storage**.</span></span>

1. <span data-ttu-id="6875d-119">Selezionare **Nuovo** per aprire il riquadro **Confronta prezzi articoli**.</span><span class="sxs-lookup"><span data-stu-id="6875d-119">Select **New** to open the **Compare item prices** pane.</span></span> <span data-ttu-id="6875d-120">Impostare le seguenti opzioni per definire quali prezzi confrontare nel report:</span><span class="sxs-lookup"><span data-stu-id="6875d-120">Set the following options to define which prices to compare in your report:</span></span>

    - <span data-ttu-id="6875d-121">Sulla scheda dettaglio **Parametri**, assegnare al report un **Nome** univoco e usare i campi nelle sezioni **Prezzi in sospeso da confrontare** e **Prezzi utilizzati per il confronto** per definire quali prezzi e date confrontare.</span><span class="sxs-lookup"><span data-stu-id="6875d-121">On the **Parameters** FastTab, give the report a unique **Name** and use the fields in the **Pending prices to compare** and **Prices used for comparison** sections to define which prices and dates to compare.</span></span>
    - <span data-ttu-id="6875d-122">Sulla scheda dettaglio **Record da includere**, impostare filtri e vincoli per definire quali dati includere nel report.</span><span class="sxs-lookup"><span data-stu-id="6875d-122">On the **Records to include** FastTab, set up filters and constraints to define which data to include in the report.</span></span>
    - <span data-ttu-id="6875d-123">Sulla scheda dettaglio **Esegui in background**, impostare come, quando e la frequenza con cui si desidera generare il report.</span><span class="sxs-lookup"><span data-stu-id="6875d-123">On the **Run in the background** FastTab, set up how, when, and the frequency at which you want to generate the report.</span></span>
    > [!NOTE]
    > <span data-ttu-id="6875d-124">Questo report viene sempre eseguito come parte di un processo batch.</span><span class="sxs-lookup"><span data-stu-id="6875d-124">This report is always executed as part of a batch job.</span></span>

1. <span data-ttu-id="6875d-125">Selezionare **OK** per applicare le impostazioni e chiudere il riquadro.</span><span class="sxs-lookup"><span data-stu-id="6875d-125">Select **OK** to apply your settings and close the pane.</span></span>

1. <span data-ttu-id="6875d-126">Una volta completato, il processo batch viene elencato nella pagina **Confronta prezzi degli articoli in magazzino**.</span><span class="sxs-lookup"><span data-stu-id="6875d-126">After the batch job is completed, it will be listed on the **Compare item prices storage** page.</span></span> <span data-ttu-id="6875d-127">È possibile dover aggiornare la pagina per visualizzare il report.</span><span class="sxs-lookup"><span data-stu-id="6875d-127">You may need to refresh the page to see the report.</span></span>

## <a name="explore-the-compare-item-prices-storage-report"></a><span data-ttu-id="6875d-128">Esplorare il report in cui vengono confrontati i prezzi degli articoli in magazzino</span><span class="sxs-lookup"><span data-stu-id="6875d-128">Explore the Compare item prices storage report</span></span>

<span data-ttu-id="6875d-129">Dopo aver generato un report, puoi visualizzarlo ed esplorarlo in qualsiasi momento come segue:</span><span class="sxs-lookup"><span data-stu-id="6875d-129">After you've generated a report, you can view and explore it at any time as follows:</span></span>

1. <span data-ttu-id="6875d-130">Andare a **Gestione costi > Richieste di informazioni e report > Report costi predeterminati > Confronta prezzi degli articoli in magazzino**.</span><span class="sxs-lookup"><span data-stu-id="6875d-130">Go to **Cost management > Inquiries and reports > Predetermined cost reports > Compare item prices storage**.</span></span>

1. <span data-ttu-id="6875d-131">Selezionare un report dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="6875d-131">Select a report from the list.</span></span>

1. <span data-ttu-id="6875d-132">Effettuare una delle seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="6875d-132">Do one of the following:</span></span>

    - <span data-ttu-id="6875d-133">Selezionare **Panoramica** per visualizzare una panoramica dei risultati del report.</span><span class="sxs-lookup"><span data-stu-id="6875d-133">Select **Overview** to get an overview of your report results.</span></span>
    - <span data-ttu-id="6875d-134">Selezionare **Visualizza dettagli** per visualizzare una visione più dettagliata del report</span><span class="sxs-lookup"><span data-stu-id="6875d-134">Select **View details** to get a more detailed view of your report</span></span>

1. <span data-ttu-id="6875d-135">Una volta aperte le visualizzazioni selezionate, è possibile effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="6875d-135">After the selected view opens, you can do the following:</span></span>

    - <span data-ttu-id="6875d-136">Selezionare quasi qualsiasi intestazione di colonna per ordinare o filtrare la tabella in base ai valori di quella colonna, proprio come per la maggior parte dei moduli standard in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="6875d-136">Select almost any column heading to sort or filter the table by values in that column, just as with most standard forms in Supply Chain Management.</span></span> <span data-ttu-id="6875d-137">Nota che non è possibile ordinare o filtrare la colonna **Prezzo di variazione netto %** perché è un campo calcolato.</span><span class="sxs-lookup"><span data-stu-id="6875d-137">Note, you can't sort or filter the **Net change price %** column because it's a calculated field.</span></span>
    - <span data-ttu-id="6875d-138">Selezionare **Visualizzazione dimensioni** per aprire un riquadro in cui è possibile scegliere quale colonna dimensione includere nel modulo.</span><span class="sxs-lookup"><span data-stu-id="6875d-138">Select **Dimension display** to open a pane where you can choose which dimension column to include on the form.</span></span> <span data-ttu-id="6875d-139">Impostare **Salva impostazione** su **Sì** se si desidera salvare queste impostazioni in modo che vengano conservate alla successiva apertura del report.</span><span class="sxs-lookup"><span data-stu-id="6875d-139">Set **Save setup** to **Yes** if you'd like to save these settings so they will be preserved the next time you open the report.</span></span> <span data-ttu-id="6875d-140">Selezionare **OK** per applicare le impostazioni e chiudere.</span><span class="sxs-lookup"><span data-stu-id="6875d-140">Select **OK** to apply your settings and close.</span></span>
    - <span data-ttu-id="6875d-141">Selezionare una riga qualsiasi nel modulo, quindi selezionare **Visualizza dettagli** per visualizzare ulteriori informazioni sull'articolo selezionato.</span><span class="sxs-lookup"><span data-stu-id="6875d-141">Select any row in the form and then select **View details** to see more information about the selected item.</span></span> <span data-ttu-id="6875d-142">Da qui sarà possibile approfondire i dati.</span><span class="sxs-lookup"><span data-stu-id="6875d-142">You'll be able to drill down into the data from here.</span></span>
    - <span data-ttu-id="6875d-143">Selezionare una riga qualsiasi nel modulo, quindi selezionare **Visualizza grafico di confronto** per visualizzare una rappresentazione grafica interattiva dei risultati in relazione all'articolo selezionato.</span><span class="sxs-lookup"><span data-stu-id="6875d-143">Select any row in the form and then select **View comparison chart** to see an interactive graphical representation of your results as they relate to your selected item.</span></span> <span data-ttu-id="6875d-144">È possibile esplorare questi risultati selezionando vari elementi grafici nella legenda del grafico e nel grafico.</span><span class="sxs-lookup"><span data-stu-id="6875d-144">You can explore these results by selecting various graphical elements in the chart and chart legend.</span></span>
    - <span data-ttu-id="6875d-145">Selezionare una riga qualsiasi nel modulo, quindi selezionare **Visualizza dettagli calcolo** per visualizzare ulteriori informazioni sui calcoli correlati all'articolo selezionato.</span><span class="sxs-lookup"><span data-stu-id="6875d-145">Select any row in the form and then select **View calculation details** to see more information about calculations related to the selected item.</span></span> <span data-ttu-id="6875d-146">Da qui sarà possibile approfondire i dati.</span><span class="sxs-lookup"><span data-stu-id="6875d-146">You'll be able to drill down into the data from here.</span></span>

## <a name="export-the-compare-item-prices-storage-report"></a><span data-ttu-id="6875d-147">Esportare il report in cui vengono confrontati i prezzi degli articoli in magazzino</span><span class="sxs-lookup"><span data-stu-id="6875d-147">Export the Compare item prices storage report</span></span>

<span data-ttu-id="6875d-148">Ogni report generato viene archiviato nell'entità di dati **Confronta prezzi degli articoli**.</span><span class="sxs-lookup"><span data-stu-id="6875d-148">Each report that you generate is stored in the **Compare item prices** data entity.</span></span> <span data-ttu-id="6875d-149">È possibile utilizzare le funzionalità standard di gestione dei dati di Supply Chain Management per esportare i dati da questa entità in qualsiasi formato di dati supportato, incluso CSV o Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="6875d-149">You can use the standard data management features of Supply Chain Management to export data from this entity to any supported data format, including CSV or Microsoft Excel.</span></span>

<span data-ttu-id="6875d-150">Il seguente è un esempio di come esportare nel report **Confronta prezzi degli articoli in magazzino**:</span><span class="sxs-lookup"><span data-stu-id="6875d-150">The following is an example of how to export a **Compare item prices storage** report:</span></span>

1. <span data-ttu-id="6875d-151">Andare a **Amministrazione sistema > Aree di lavoro > Gestione dati**.</span><span class="sxs-lookup"><span data-stu-id="6875d-151">Go to **System administration > Workspaces > Data management**.</span></span>

1. <span data-ttu-id="6875d-152">Selezionare il pulsante **Esporta** nella sezione **Gestione dati**.</span><span class="sxs-lookup"><span data-stu-id="6875d-152">Select the **Export** button in the **Data management** section.</span></span>

1. <span data-ttu-id="6875d-153">Viene visualizzata la pagina **Esporta** che verrà utilizzata per impostare il processo di esportazione.</span><span class="sxs-lookup"><span data-stu-id="6875d-153">The **Export** page opens, which you'll use to set up your export job.</span></span> <span data-ttu-id="6875d-154">Iniziare assegnando al processo un **Nome gruppo**.</span><span class="sxs-lookup"><span data-stu-id="6875d-154">Start by giving your job a **Group name**.</span></span>

1. <span data-ttu-id="6875d-155">Nella sezione **Entità selezionate** selezionare **Aggiungi entità** per aprire una finestra di dialogo in cui è possibile impostare le seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="6875d-155">In the **Selected entities** section, select **Add entity** to open a dialog box where you can set the following options:</span></span>

    - <span data-ttu-id="6875d-156">**Nome entità** - Selezionare **Confronta prezzi articoli**.</span><span class="sxs-lookup"><span data-stu-id="6875d-156">**Entity name** - Select **Compare item prices**.</span></span>
    - <span data-ttu-id="6875d-157">**Formato dei dati di destinazione** - Scegliere il formato in cui si desidera esportare.</span><span class="sxs-lookup"><span data-stu-id="6875d-157">**Target data format** - Choose the format that you want to export to.</span></span>

1. <span data-ttu-id="6875d-158">Selezionare **Aggiungi** per aggiungere la nuova riga e quindi selezionare **Chiudi** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="6875d-158">Select **Add** to add the new row and then select **Close** to close the dialog box.</span></span>

1. <span data-ttu-id="6875d-159">Di solito si esporta un report alla volta.</span><span class="sxs-lookup"><span data-stu-id="6875d-159">Usually you'll export one report at a time.</span></span> <span data-ttu-id="6875d-160">Per fare ciò, impostare un **Filtro** per la riga appena aggiunta al riquadro **Richiesta informazioni**.</span><span class="sxs-lookup"><span data-stu-id="6875d-160">To do this, set up a **Filter** for the row you just added to the **Inquiry** pane.</span></span> <span data-ttu-id="6875d-161">Questo permetterà di definire i report dell'entità **Confronta prezzi articoli** che si desidera includere nell'esportazione.</span><span class="sxs-lookup"><span data-stu-id="6875d-161">This will let you define which reports from the **Compare item prices** entity that you want to include in your export.</span></span> <span data-ttu-id="6875d-162">Impostare le seguenti opzioni di filtro per esportare un singolo report:</span><span class="sxs-lookup"><span data-stu-id="6875d-162">Set the following filter options to export a single report:</span></span>

    - <span data-ttu-id="6875d-163">Sulla scheda **Intervallo**, selezionare **Aggiungi** per aggiungere una nuova riga.</span><span class="sxs-lookup"><span data-stu-id="6875d-163">On the **Range** tab, select **Add** to add a new row.</span></span>
    - <span data-ttu-id="6875d-164">Impostare **Tabella** su **Confronta prezzi articoli**.</span><span class="sxs-lookup"><span data-stu-id="6875d-164">Set **Table** to **Compare item prices**.</span></span>
    - <span data-ttu-id="6875d-165">Impostare **Tabella derivata** su **Confronta prezzi articoli**.</span><span class="sxs-lookup"><span data-stu-id="6875d-165">Set **Derived table** to **Compare item prices**.</span></span>
    - <span data-ttu-id="6875d-166">Impostare **Campo** sul campo in base al quale si desidera filtrare.</span><span class="sxs-lookup"><span data-stu-id="6875d-166">Set **Field** to the field that you want to filter by.</span></span> <span data-ttu-id="6875d-167">Di solito si usa **Nome esecuzione** o **Tempo esecuzione**.</span><span class="sxs-lookup"><span data-stu-id="6875d-167">Usually you'll use **Execution name** or **Execution time**.</span></span>
    - <span data-ttu-id="6875d-168">Impostare **Criteri** sul valore del campo selezionato che si desidera cercare (il nome del report o l'ora in cui il report è stato generato).</span><span class="sxs-lookup"><span data-stu-id="6875d-168">Set **Criteria** to the value from your selected field that you want to look for (either the name of the report or the time the report was generated).</span></span>
    - <span data-ttu-id="6875d-169">Se necessario, aggiungere più righe alla tabella **Intervallo** fino a quando non è stato identificato in modo univoco il report che si sta cercando.</span><span class="sxs-lookup"><span data-stu-id="6875d-169">If necessary, add more rows to the **Range** table until you have uniquely identified the report that you're looking for.</span></span>

1. <span data-ttu-id="6875d-170">Selezionare **OK** per salvare le impostazioni e chiudere.</span><span class="sxs-lookup"><span data-stu-id="6875d-170">Select **OK** to save your settings and close.</span></span>

1. <span data-ttu-id="6875d-171">Selezionare **Salva** per salvare l'impostazione dell'esportazione.</span><span class="sxs-lookup"><span data-stu-id="6875d-171">Select **Save** to save your export setup.</span></span>

1. <span data-ttu-id="6875d-172">Aprire la scheda **Opzioni di esportazione** e selezionare **Esporta ora** per generare il file di esportazione.</span><span class="sxs-lookup"><span data-stu-id="6875d-172">Open the **Export options** tab and select **Export now** to generate the export file.</span></span>

1. <span data-ttu-id="6875d-173">Viene visualizzata la pagina **Riepilogo dell'esecuzione** in cui è possibile vedere lo stato del processo di esportazione e un elenco di entità esportate.</span><span class="sxs-lookup"><span data-stu-id="6875d-173">The **Execution summary** page opens, where you can see the status of your export job and a list of entities that were exported.</span></span> <span data-ttu-id="6875d-174">Selezionare l'entità **Confronta prezzi articoli** elencata nell'area **Stato elaborazione entità** e quindi selezionare **Scarica file** per scaricare i dati esportati da tale entità.</span><span class="sxs-lookup"><span data-stu-id="6875d-174">Select the **Compare item prices** entity listed in the **Entity processing status** area and then select **Download file** to download the data exported from that entity.</span></span>

<span data-ttu-id="6875d-175">Per ulteriori informazioni su come utilizzare la gestione dei dati per esportare i dati, vedere [Panoramica processi di importazione ed esportazione dati](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).</span><span class="sxs-lookup"><span data-stu-id="6875d-175">For more information about how to use data management to export data, see [Data import and export jobs overview](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).</span></span>
