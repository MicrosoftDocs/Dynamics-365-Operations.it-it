---
title: Pianificare la creazione del lavoro nel corso del ciclo
description: Questo argomento descrive come configurare e utilizzare il metodo di elaborazione del ciclo Pianifica creazione lavoro.
author: perlynne
manager: mirzaab
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPostMethod, WHSWavePostMethodTaskConfig, WHSWaveTemplateTable, WHSParameters, WHSWaveTableListPage, WHSWorkTableListPage, WHSWorkTable, BatchJobEnhanced, WHSPlannedWorkOrder
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-01-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: ed8f43c7db139b7b16ac6901d5db56ba2f021690
ms.sourcegitcommit: b7a7a14f8650913f6797ae1c4a82ad8adfe415fd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2021
ms.locfileid: "5078276"
---
# <a name="schedule-work-creation-during-wave"></a><span data-ttu-id="ddff9-103">Pianificare la creazione del lavoro nel corso del ciclo</span><span class="sxs-lookup"><span data-stu-id="ddff9-103">Schedule work creation during wave</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ddff9-104">Utilizza la funzionalità *Pianifica creazione lavoro* come parte del processo di creazione dei cicli per aumentare la velocità di elaborazione dei cicli facendo in modo che il sistema crei il lavoro utilizzando l'elaborazione parallela.</span><span class="sxs-lookup"><span data-stu-id="ddff9-104">Use the *Schedule work creation* feature as part of your waving process to help increase wave processing throughput by having the system create work using parallel processing.</span></span>

<span data-ttu-id="ddff9-105">Quando la funzionalità è abilitata, viene automaticamente creato il lavoro pianificato, che il sistema elaborerà in seguito per creare il lavoro effettivo.</span><span class="sxs-lookup"><span data-stu-id="ddff9-105">When the functionality is enabled, planned work will automatically get created, which the system will eventually process to create actual work.</span></span> <span data-ttu-id="ddff9-106">Se il numero di righe di carico del ciclo raggiunge una soglia predeterminata, il sistema creerà il lavoro effettivo più rapidamente applicando l'elaborazione parallela e asincrona.</span><span class="sxs-lookup"><span data-stu-id="ddff9-106">If the number of wave load lines reaches a predetermined threshold, the system will create actual work more quickly by applying parallel, asynchronous processing.</span></span>

## <a name="enable-the-schedule-work-creation-feature"></a><span data-ttu-id="ddff9-107">Abilitare la funzione Pianifica creazione lavoro</span><span class="sxs-lookup"><span data-stu-id="ddff9-107">Enable the Schedule work creation feature</span></span>

### <a name="enable-the-feature-in-feature-management"></a><span data-ttu-id="ddff9-108">Abilitare la funzionalità nella gestione delle funzionalità</span><span class="sxs-lookup"><span data-stu-id="ddff9-108">Enable the feature in feature management</span></span>

<span data-ttu-id="ddff9-109">Prima di poter utilizzare la funzionalità *Pianifica creazione lavoro*, è necessario attivarla nel sistema.</span><span class="sxs-lookup"><span data-stu-id="ddff9-109">Before you can use the *Schedule work creation* feature, it must be turned on in your system.</span></span> <span data-ttu-id="ddff9-110">Gli amministratori possono utilizzare l'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzionalità e attivarla se necessario.</span><span class="sxs-lookup"><span data-stu-id="ddff9-110">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="ddff9-111">Nell'area di lavoro, la funzionalità è elencata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="ddff9-111">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="ddff9-112">**Modulo:** *Gestione Magazzino*</span><span class="sxs-lookup"><span data-stu-id="ddff9-112">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="ddff9-113">**Nome funzionalità:** *Pianifica creazione lavoro*</span><span class="sxs-lookup"><span data-stu-id="ddff9-113">**Feature name:** *Schedule work creation*</span></span>

> [!NOTE]
> <span data-ttu-id="ddff9-114">La funzionalità *Blocco lavoro a livello di organizzazione* deve essere abilitata prima di poter abilitare *Pianifica creazione lavoro*.</span><span class="sxs-lookup"><span data-stu-id="ddff9-114">The *Organization-wide work blocking* feature must be enabled before you can enable *Schedule work creation*.</span></span>

### <a name="manually-enable-batch-processing-of-waves"></a><span data-ttu-id="ddff9-115">Abilitare manualmente l'elaborazione in batch dei cicli</span><span class="sxs-lookup"><span data-stu-id="ddff9-115">Manually enable batch processing of waves</span></span>

<span data-ttu-id="ddff9-116">Per sfruttare un metodo asincrono parallelo per creare il lavoro di magazzino, il processo di ciclo deve essere eseguito in batch.</span><span class="sxs-lookup"><span data-stu-id="ddff9-116">To take advantage of a parallel asynchronous method to create warehouse work, your wave process must be running in batch.</span></span> <span data-ttu-id="ddff9-117">Per configurarlo:</span><span class="sxs-lookup"><span data-stu-id="ddff9-117">To set this up:</span></span>

1. <span data-ttu-id="ddff9-118">Andare a  **Gestione magazzino\>Imposta \> Parametri di gestione magazzino**.</span><span class="sxs-lookup"><span data-stu-id="ddff9-118">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>

1. <span data-ttu-id="ddff9-119">Nella scheda **Generale**, imposta **Elabora cicli in batch** su *Sì*.</span><span class="sxs-lookup"><span data-stu-id="ddff9-119">On the **General** tab, set **Process waves in batch** to *Yes*.</span></span> <span data-ttu-id="ddff9-120">Facoltativamente, puoi anche selezionare un **Gruppo batch elaborazione ondata** per impedire che l'elaborazione della coda batch venga eseguita contemporaneamente ad altri processi.</span><span class="sxs-lookup"><span data-stu-id="ddff9-120">Optionally, you can also select a dedicated **Wave processing batch group** to prevent your batch queue processing from running at the same time as other processes.</span></span>

1. <span data-ttu-id="ddff9-121">Imposta il **Tempo di attesa per il blocco (ms)**, che si applica quando il sistema elabora più ondate contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="ddff9-121">Set the **Wait for lock (ms) time**, which applies when the system is processing several waves at the same time.</span></span> <span data-ttu-id="ddff9-122">Per la maggior parte dei processi di ondata più grandi, è consigliabile impostare un valore pari a *60000*.</span><span class="sxs-lookup"><span data-stu-id="ddff9-122">For most larger waving processes, we recommend a value of *60000*.</span></span>

### <a name="manually-enable-the-new-wave-step-method-for-existing-wave-templates"></a><span data-ttu-id="ddff9-123">Abilitare manualmente il nuovo metodo del passaggio ondata per i modelli di ondata esistenti</span><span class="sxs-lookup"><span data-stu-id="ddff9-123">Manually enable the new wave step method for existing wave templates</span></span>

<span data-ttu-id="ddff9-124">Inizia creando il nuovo metodo di passaggio di ondata e abilitandolo per l'elaborazione parallela di attività asincrone.</span><span class="sxs-lookup"><span data-stu-id="ddff9-124">Start by creating the new wave step method and enabling it for parallel asynchronous task processing.</span></span>

1. <span data-ttu-id="ddff9-125">Andare a  **Gestione magazzino \> Imposta \> Ondate \> Metodi di elaborazione ondata**.</span><span class="sxs-lookup"><span data-stu-id="ddff9-125">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>

1. <span data-ttu-id="ddff9-126">Selezionare  **Rigenera metodo** e notare come *WHSScheduleWorkCreationWaveStepMethod* sia stato aggiunto all'elenco dei metodi di elaborazione ondata che puoi utilizzare nei modelli di ondate di spedizione.</span><span class="sxs-lookup"><span data-stu-id="ddff9-126">Select  **Regenerate method** and note that *WHSScheduleWorkCreationWaveStepMethod* has been added to the list of wave process methods you can use in your shipping wave templates.</span></span>

1. <span data-ttu-id="ddff9-127">Selezionare il record con il **Nome metodo** *WHSScheduleWorkCreationWaveStepMethod* e selezionare **Configurazione attività**.</span><span class="sxs-lookup"><span data-stu-id="ddff9-127">Select the record with the **Method name** *WHSScheduleWorkCreationWaveStepMethod* and select **Task configuration**.</span></span>

1. <span data-ttu-id="ddff9-128">Per aggiungere una nuova riga alla griglia, selezionare **Nuovo** nel riquadro azioni e utilizzare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ddff9-128">To add a new row to the grid, select **New** on the Action Pane and use the following settings:</span></span>

    - <span data-ttu-id="ddff9-129">**Magazzino**: seleziona il magazzino che utilizzerai per l'elaborazione di Pianifica creazione lavoro.</span><span class="sxs-lookup"><span data-stu-id="ddff9-129">**Warehouse** - Select the warehouse you will use to schedule work creation processing.</span></span>

    - <span data-ttu-id="ddff9-130">**Numero massimo di attività batch**: specifica un numero massimo di attività batch.</span><span class="sxs-lookup"><span data-stu-id="ddff9-130">**Maximum number of batch tasks** - Specify a maximum number of batch tasks.</span></span> <span data-ttu-id="ddff9-131">Nella maggior parte dei casi, questo valore dovrebbe essere compreso tra 8 e 16, tuttavia è consigliabile sperimentare l'impostazione ottimale in base ai tuoi scenari.</span><span class="sxs-lookup"><span data-stu-id="ddff9-131">In most cases, this value should be in the range from 8-16, however we recommend that you experiment with the optimal setting based on your scenarios.</span></span>

    - <span data-ttu-id="ddff9-132">**Gruppo batch elaborazione ondata**: selezionare un gruppo batch di elaborazione ondata dedicato per ottimizzare l'elaborazione della coda batch.</span><span class="sxs-lookup"><span data-stu-id="ddff9-132">**Wave processing batch group** - Select a dedicated wave processing batch group to optimize your batch queue processing.</span></span>

<span data-ttu-id="ddff9-133">Ora sei pronto per aggiornare un modello di ondata esistente (o crearne uno nuovo) per il metodo di elaborazione ondata *Pianifica creazione lavoro*.</span><span class="sxs-lookup"><span data-stu-id="ddff9-133">Now you are ready to update an existing wave template (or create a new one) to use the *Schedule work creation* wave processing method.</span></span>

1. <span data-ttu-id="ddff9-134">Passare a  **Gestione magazzino \> Imposta \> Ondate \> Modelli ondata**.</span><span class="sxs-lookup"><span data-stu-id="ddff9-134">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>

1. <span data-ttu-id="ddff9-135">Selezionare **Modifica** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="ddff9-135">Select **Edit** on the Action Pane.</span></span>

1. <span data-ttu-id="ddff9-136">Nel riquadro dell'elenco, seleziona il modello di ondata che desideri aggiornare (se stai testando utilizzando i dati demo, puoi usare *Spedizione predefinita 24*).</span><span class="sxs-lookup"><span data-stu-id="ddff9-136">In the list pane, select the wave template you would like to update (if you are testing using demo data, then you could use *24 Shipping default*).</span></span>

1. <span data-ttu-id="ddff9-137">Espandi la Scheda dettaglio **Metodi** e seleziona la riga con il **Nome** *Pianifica creazione lavoro* nella griglia **Metodi rimanenti**.</span><span class="sxs-lookup"><span data-stu-id="ddff9-137">Expand the **Methods** FastTab and select the row with the **Name** *Schedule work creation* in the **Remaining methods** grid.</span></span>

1. <span data-ttu-id="ddff9-138">Seleziona la freccia che punta alla colonna **Metodi selezionati** per spostare la riga selezionata in quella colonna.</span><span class="sxs-lookup"><span data-stu-id="ddff9-138">Select the arrow pointing to the **Selected methods** column to move the selected row to that column.</span></span> <span data-ttu-id="ddff9-139">Puoi avere solo un metodo selezionato alla volta che utilizza *WHSScheduleWorkCreationWaveStepMethod* o *createWork*, quindi la riga esistente con **Nome del metodo** *createWork* viene automaticamente spostata nella griglia **Metodi rimanenti**.</span><span class="sxs-lookup"><span data-stu-id="ddff9-139">(You can only have one selected method at a time that uses either *WHSScheduleWorkCreationWaveStepMethod* or *createWork*, so the existing row with **Method name** *createWork* is automatically moved to the **Remaining methods** grid.)</span></span>

## <a name="set-wave-task-processing-threshold-data"></a><span data-ttu-id="ddff9-140">Impostare i dati della soglia di elaborazione dell'attività di ondata</span><span class="sxs-lookup"><span data-stu-id="ddff9-140">Set wave task processing threshold data</span></span>

<span data-ttu-id="ddff9-141">Il sistema creerà i dati della soglia di elaborazione dell'attività di ondata predefinita la prima volta che un processo di ondata viene eseguito utilizzando un'elaborazione basata su attività.</span><span class="sxs-lookup"><span data-stu-id="ddff9-141">The system will create default wave task processing threshold data the first time a wave process runs using any task-based processing.</span></span> <span data-ttu-id="ddff9-142">I dati vengono utilizzati per controllare quando l'elaborazione di ondata verrà eseguita in modo asincrono e sarà basata su attività, il che consente di elaborare e creare lavoro in parallelo.</span><span class="sxs-lookup"><span data-stu-id="ddff9-142">The data is used to control when wave processing will run asynchronously and be task-based, which enables it to process and create work in parallel.</span></span>

<span data-ttu-id="ddff9-143">I dati predefiniti utilizzeranno inizialmente un valore di soglia di 15 per il numero minimo di righe di carico (MINIMUMWAVELOADLINES).</span><span class="sxs-lookup"><span data-stu-id="ddff9-143">The default data will initially use a threshold value of 15 for the minimum number of load lines (MINIMUMWAVELOADLINES).</span></span> <span data-ttu-id="ddff9-144">Ciò significa che quando il sistema elabora un'ondata con più di 15 righe di carico, utilizzerà l'elaborazione delle attività asincrone.</span><span class="sxs-lookup"><span data-stu-id="ddff9-144">This means that when the system processes a wave with more than 15 loads lines, it will use asynchronous task processing.</span></span> <span data-ttu-id="ddff9-145">È possibile inserire/aggiornare manualmente questi dati nella tabella **WHSWaveTaskProcessingThresholdParameters** negli ambienti di test, ma se è necessario modificare questa impostazione in un ambiente di produzione, è necessario contattare il supporto Microsoft per richiedere l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="ddff9-145">You can manually insert/update this data in the **WHSWaveTaskProcessingThresholdParameters** table in your test environments, but if you need to change this setting in a production environment, you must contact Microsoft Support to request the update.</span></span>

## <a name="work-with-the-feature"></a><span data-ttu-id="ddff9-146">Utilizzare la funzione</span><span class="sxs-lookup"><span data-stu-id="ddff9-146">Work with the feature</span></span>

<span data-ttu-id="ddff9-147">Quando la funzionalità *Pianifica creazione lavoro* è abilitata, l'elaborazione dell'ondata creerà il lavoro pianificato, che verrà in seguito utilizzato dal nuovo processo di creazione del lavoro.</span><span class="sxs-lookup"><span data-stu-id="ddff9-147">When the *Schedule work creation* functionality is enabled, wave processing will create planned work, which will eventually be used by the new work creation process.</span></span> <span data-ttu-id="ddff9-148">Durante la creazione del lavoro, il lavoro verrà bloccato utilizzando la funzionalità *Blocco lavoro a livello di organizzazione*.</span><span class="sxs-lookup"><span data-stu-id="ddff9-148">During work creation, the work will be blocked using the *Organization-wide work blocking* feature.</span></span>

<span data-ttu-id="ddff9-149">Il diagramma di flusso seguente mostra come viene creato il lavoro pianificato durante l'elaborazione dell'ondata.</span><span class="sxs-lookup"><span data-stu-id="ddff9-149">The following flowchart shows how planned work is created during wave processing.</span></span>

![Programma creazione lavoro](media/schedule-work-creation-process.png)

### <a name="planned-work"></a><span data-ttu-id="ddff9-151">Lavoro pianificato</span><span class="sxs-lookup"><span data-stu-id="ddff9-151">Planned work</span></span>

<span data-ttu-id="ddff9-152">La pagina **Dettagli lavoro pianificato** (**Gestione magazzino \> Lavoro \> Dettagli del lavoro pianificato**) mostra le informazioni sul lavoro pianificato, che viene inizialmente creato durante l'elaborazione dell'ondata.</span><span class="sxs-lookup"><span data-stu-id="ddff9-152">The **Planned work details** page (**Warehouse management \> Work \> Planned work details**) shows information about the planned work, which is initially created during wave processing.</span></span> <span data-ttu-id="ddff9-153">Sono disponibili i seguenti valori di **Stato processo**:</span><span class="sxs-lookup"><span data-stu-id="ddff9-153">The following **Process status** values are available:</span></span>

- <span data-ttu-id="ddff9-154">**In coda**: il lavoro pianificato attende di essere utilizzato per creare lavoro.</span><span class="sxs-lookup"><span data-stu-id="ddff9-154">**Queued** - The planned work is waiting to be used to create work.</span></span>
- <span data-ttu-id="ddff9-155">**Completato**: il lavoro pianificato è stato utilizzato per creare lavoro.</span><span class="sxs-lookup"><span data-stu-id="ddff9-155">**Completed** - The planned work has been used to create work.</span></span>
- <span data-ttu-id="ddff9-156">**Non riuscita**: l'elaborazione dell'ondata non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="ddff9-156">**Failed** – The wave processing has failed.</span></span> <span data-ttu-id="ddff9-157">Notare che il lavoro pianificato può essere in uno stato **Non riuscita** con o senza lavoro effettivo correlato.</span><span class="sxs-lookup"><span data-stu-id="ddff9-157">Note that the planned work can be in a **Failed** state with or without related actual work.</span></span> <span data-ttu-id="ddff9-158">Quando il processo di creazione del lavoro effettivo non riesce, il lavoro effettivo rimane nello stato *Annullato*.</span><span class="sxs-lookup"><span data-stu-id="ddff9-158">When the actual work creation process fails, the actual work remains in status *Cancelled*.</span></span>

### <a name="batch-job-for-the-work-creation-process"></a><span data-ttu-id="ddff9-159">Processo batch per il processo di creazione del lavoro</span><span class="sxs-lookup"><span data-stu-id="ddff9-159">Batch job for the work creation process</span></span>

<span data-ttu-id="ddff9-160">Per visualizzare i processi batch per l'elaborazione delle ondate, selezionare **Processi batch** nel riquadro azioni della pagina **Tutte le ondate**.</span><span class="sxs-lookup"><span data-stu-id="ddff9-160">To view the batch jobs for processing waves, select **Batch jobs** on the Action Pane on the **All waves** page.</span></span>

<span data-ttu-id="ddff9-161">Da qui, è possibile visualizzare tutti i dettagli dell'attività batch per ciascuno degli ID processo batch.</span><span class="sxs-lookup"><span data-stu-id="ddff9-161">From here, you can view all the batch task details for each of the batch job IDs.</span></span>
