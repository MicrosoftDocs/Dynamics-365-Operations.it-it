---
title: Creazione di ordini di lavoro
description: Nell'argomento viene descritto come creare ordini di lavoro in Gestione cespiti.
author: johanhoffmann
manager: tfehr
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetMaintenancePlan, EntAssetObjectCalendarListPage, EntAssetObjectCalendarListPagePoolsOpen
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 76306fb31e7e5297e6a5d64b97b5bd09b64349ee
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500576"
---
# <a name="creating-work-orders"></a><span data-ttu-id="dfa8e-103">Creazione di ordini di lavoro</span><span class="sxs-lookup"><span data-stu-id="dfa8e-103">Creating work orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="dfa8e-104">Dopo aver programmato processi di manutenzione preventiva, il passaggio successivo prevede la creazione di ordini di lavoro per i processi.</span><span class="sxs-lookup"><span data-stu-id="dfa8e-104">After you've scheduled preventive maintenance jobs, the next step is to create work orders for them.</span></span> <span data-ttu-id="dfa8e-105">È possibile completare questo passaggio utilizzando uno dei programmi di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="dfa8e-105">You can complete this step by using one of the maintenance schedules.</span></span> <span data-ttu-id="dfa8e-106">I processi programmati in un programma di manutenzione possono avere diversi tipi di riferimenti, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="dfa8e-106">The scheduled jobs in a maintenance schedule can have different reference types, as described in the following table.</span></span>

| <span data-ttu-id="dfa8e-107">Tipo di riferimento</span><span class="sxs-lookup"><span data-stu-id="dfa8e-107">Reference type</span></span> | <span data-ttu-id="dfa8e-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dfa8e-108">Description</span></span> |
|---|---|
| <span data-ttu-id="dfa8e-109">Piani di manutenzione</span><span class="sxs-lookup"><span data-stu-id="dfa8e-109">Maintenance plans</span></span> | <span data-ttu-id="dfa8e-110">Processi di manutenzione preventiva basati su tipi di piani di manutenzione *Tempo* o *Contatore*.</span><span class="sxs-lookup"><span data-stu-id="dfa8e-110">Preventive maintenance jobs that are based on the *Time* or *Counter* maintenance plan type.</span></span> |
| <span data-ttu-id="dfa8e-111">Cicli di manutenzione</span><span class="sxs-lookup"><span data-stu-id="dfa8e-111">Maintenance rounds</span></span> | <span data-ttu-id="dfa8e-112">Processi di manutenzione preventiva contenenti vari cespiti che richiedono un tipo di manutenzione simile.</span><span class="sxs-lookup"><span data-stu-id="dfa8e-112">Preventive maintenance jobs that contain several assets that require a similar type of maintenance.</span></span> |
| <span data-ttu-id="dfa8e-113">Richiesta di intervento di manutenzione</span><span class="sxs-lookup"><span data-stu-id="dfa8e-113">Maintenance request</span></span> | <span data-ttu-id="dfa8e-114">Una richiesta creata manualmente per la manutenzione o la riparazione di un cespite.</span><span class="sxs-lookup"><span data-stu-id="dfa8e-114">A manually created request for maintenance or repair of an asset.</span></span> <span data-ttu-id="dfa8e-115">Questa richiesta può essere convertita in un ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="dfa8e-115">This request can be converted to a work order.</span></span> |

## <a name="create-work-orders-based-on-your-maintenance-schedule"></a><span data-ttu-id="dfa8e-116">Creare ordini di lavoro in base al proprio programma di manutenzione</span><span class="sxs-lookup"><span data-stu-id="dfa8e-116">Create work orders based on your maintenance schedule</span></span>

<span data-ttu-id="dfa8e-117">Per creare ordini di lavoro basati sul programma di manutenzione, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="dfa8e-117">To create work orders that are based on your maintenance schedule, follow these steps.</span></span>

1. <span data-ttu-id="dfa8e-118">Apri una delle seguenti pagine, a seconda di come desideri selezionare gli elementi della pianificazione per i tuoi ordini di lavoro:</span><span class="sxs-lookup"><span data-stu-id="dfa8e-118">Open one of the following pages, depending on how you want to select schedule items for your work orders:</span></span>

    - <span data-ttu-id="dfa8e-119">Tutti i programmi di manutenzione (**Gestione cespite \> Programma di gestione \> Tutti i programmi di manutenzione**)</span><span class="sxs-lookup"><span data-stu-id="dfa8e-119">All maintenance schedule (**Asset management \> Management schedule \> All maintenance schedule**)</span></span>
    - <span data-ttu-id="dfa8e-120">Apri le righe dei programmi di manutenzione (**Gestione cespite \> Programma di gestione \> Apri righe programmi di manutenzione**)</span><span class="sxs-lookup"><span data-stu-id="dfa8e-120">Open maintenance schedule lines (**Asset management \> Management schedule \> Open maintenance schedule lines**)</span></span>
    - <span data-ttu-id="dfa8e-121">Apri i pool dei programmi di manutenzione (**Gestione cespite \> Programma di gestione \> Apri pool programmi di manutenzione**)</span><span class="sxs-lookup"><span data-stu-id="dfa8e-121">Open maintenance schedule pools (**Asset management \> Management schedule \> Open maintenance schedule pools**)</span></span>

1. <span data-ttu-id="dfa8e-122">Nella griglia seleziona la casella di controllo per ogni processo di manutenzione pianificata per cui desideri creare un ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="dfa8e-122">In the grid, select the check box for every scheduled maintenance job that you want to create a work order for.</span></span> <span data-ttu-id="dfa8e-123">Quindi, nel riquadro azioni, seleziona **Ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="dfa8e-123">Then, on the Action Pane, select **Work order**.</span></span>

    <span data-ttu-id="dfa8e-124">Viene visualizzata la finestra di dialogo **Crea ordini di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="dfa8e-124">The **Create work orders** dialog box appears.</span></span> <span data-ttu-id="dfa8e-125">Il campo **Ore previste manutenzione** mostra il numero totale di ore previste per le righe selezionate.</span><span class="sxs-lookup"><span data-stu-id="dfa8e-125">The **Maintenance forecast hours** field shows the total number of forecast hours for the selected lines.</span></span>

    ![Finestra di dialogo Crea ordini di lavoro](media/18-preventive-maintenance.png)

1. <span data-ttu-id="dfa8e-127">Nella sezione **Parametri**, specificare il numero di ordini di lavoro da creare.</span><span class="sxs-lookup"><span data-stu-id="dfa8e-127">In the **Parameters** section, specify the number of work orders that should be created.</span></span> <span data-ttu-id="dfa8e-128">Consente di selezionare una delle opzioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="dfa8e-128">Select one of the following options:</span></span>

    - <span data-ttu-id="dfa8e-129">**Un ordine di lavoro per riga** - Crea un ordine di lavoro per riga del programma di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="dfa8e-129">**One work order per line** – Create one work order per maintenance schedule line.</span></span>
    - <span data-ttu-id="dfa8e-130">**Un ordine di lavoro per** - Crea ordini di lavoro raggruppati in base alle impostazioni delle altre opzioni che diventano disponibili quando selezioni questa opzione.</span><span class="sxs-lookup"><span data-stu-id="dfa8e-130">**One work order per** – Create work orders that are grouped according to the settings of the other options that become available when you select this option.</span></span>

1. <span data-ttu-id="dfa8e-131">Nel campo **Tipo di ordine di lavoro** seleziona il tipo di ordine di lavoro da utilizzare per tutti gli ordini di lavoro creati.</span><span class="sxs-lookup"><span data-stu-id="dfa8e-131">In the **Work order type** field, select the work order type to use for all the work orders that you create.</span></span>
1. <span data-ttu-id="dfa8e-132">Seleziona **OK** per creare gli ordini di lavoro in base alle tue impostazioni.</span><span class="sxs-lookup"><span data-stu-id="dfa8e-132">Select **OK** to create the work orders according to your settings.</span></span>

## <a name="group-work-order-lines-that-are-automatically-created-while-a-maintenance-plan-runs"></a><span data-ttu-id="dfa8e-133">Raggruppare le righe ordine di lavoro che vengono create automaticamente durante l'esecuzione di un piano di manutenzione</span><span class="sxs-lookup"><span data-stu-id="dfa8e-133">Group work order lines that are automatically created while a maintenance plan runs</span></span>

[!INCLUDE [preview-banner-section](../../../includes/preview-banner-section.md)]

<span data-ttu-id="dfa8e-134">Questa funzionalità consente di definire le regole per raggruppare le righe dell'ordine di lavoro in un unico ordine di lavoro quando il sistema è configurato per generare automaticamente gli ordini di lavoro, in base a un piano di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="dfa8e-134">This feature lets you define rules for grouping work order lines under a single work order when the system is set up to generate work orders automatically, based on a maintenance plan.</span></span> <span data-ttu-id="dfa8e-135">In precedenza, gli ordini di lavoro generati automaticamente potevano contenere solo una riga.</span><span class="sxs-lookup"><span data-stu-id="dfa8e-135">Previously, automatically generated work orders could contain only one line.</span></span> <span data-ttu-id="dfa8e-136">Tuttavia, ora puoi raggruppare gli ordini di lavoro per, ad esempio, cespite, tipo di cespite o unità funzionale.</span><span class="sxs-lookup"><span data-stu-id="dfa8e-136">However, you can now group work orders by, for example, asset, asset type, or functional location.</span></span> <span data-ttu-id="dfa8e-137">Gli ordini di lavoro generati manualmente potrebbero già essere raggruppati in questo modo, come descritto nella sezione precedente di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="dfa8e-137">(Manually generated work orders could already be grouped in this way, as described in the previous section of this topic.)</span></span>

### <a name="enable-grouping-for-automatically-generated-work-orders"></a><span data-ttu-id="dfa8e-138">Abilitare il raggruppamento per gli ordini di lavoro generati automaticamente</span><span class="sxs-lookup"><span data-stu-id="dfa8e-138">Enable grouping for automatically generated work orders</span></span>

<span data-ttu-id="dfa8e-139">Prima di poter utilizzare questa funzione, è necessario attivarla nel sistema.</span><span class="sxs-lookup"><span data-stu-id="dfa8e-139">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="dfa8e-140">Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla.</span><span class="sxs-lookup"><span data-stu-id="dfa8e-140">Admins can use the [feature management](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="dfa8e-141">Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="dfa8e-141">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="dfa8e-142">**Modulo:** *Gestione cespiti*</span><span class="sxs-lookup"><span data-stu-id="dfa8e-142">**Module:** *Asset Management*</span></span>
- <span data-ttu-id="dfa8e-143">**Nome funzionalità:** *(Anteprima) Applica regole per raggruppare ordini di lavoro durante l'esecuzione di un piano di manutenzione*</span><span class="sxs-lookup"><span data-stu-id="dfa8e-143">**Feature name:** *(Preview) Apply rules for grouping work orders while running a maintenance plan*</span></span>

### <a name="set-up-grouping-for-automatically-generated-work-orders"></a><span data-ttu-id="dfa8e-144">Configurare il raggruppamento per gli ordini di lavoro generati automaticamente</span><span class="sxs-lookup"><span data-stu-id="dfa8e-144">Set up grouping for automatically generated work orders</span></span>

<span data-ttu-id="dfa8e-145">Per configurare il raggruppamento per gli ordini di lavoro generati automaticamente, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="dfa8e-145">To set up grouping for automatically generated work orders, follow these steps.</span></span>

1. <span data-ttu-id="dfa8e-146">Passa a **Gestione cespiti \> Imposta \> Manutenzione preventiva \> Piani di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="dfa8e-146">Go to **Asset management \> Setup \> Preventative maintenance \> Maintenance plans**.</span></span>
1. <span data-ttu-id="dfa8e-147">Per ogni piano in cui desideri generare ordini di lavoro raggruppati, segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="dfa8e-147">For each plan where you want to generate grouped work orders, follow these steps:</span></span>

    1. <span data-ttu-id="dfa8e-148">Seleziona il piano nel riquadro dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="dfa8e-148">Select the plan in the list pane.</span></span>
    1. <span data-ttu-id="dfa8e-149">Nella Scheda dettaglio **Righe**, verifica che la casella di controllo **Creazione automatica** sia selezionata su ogni riga.</span><span class="sxs-lookup"><span data-stu-id="dfa8e-149">On the **Lines** FastTab, make sure that the **Auto create** check box is selected on every line.</span></span>

1. <span data-ttu-id="dfa8e-150">Passa a **Gestione cespiti \> Periodica \> Manutenzione preventiva \> Piani di manutenzione programmata**.</span><span class="sxs-lookup"><span data-stu-id="dfa8e-150">Go to **Asset management \> Periodic \> Preventive maintenance \> Schedule maintenance plans**.</span></span>
1. <span data-ttu-id="dfa8e-151">Nella finestra di dialogo **Piani di manutenzione programmata**, nella sezione **Periodo**, specifica l'orizzonte temporale per il piano (fino a che punto guardare avanti quando si trovano lavori di manutenzione programmata per cui generare lavoro).</span><span class="sxs-lookup"><span data-stu-id="dfa8e-151">In the **Schedule maintenance plans** dialog box, in the **Period** section, specify the time horizon for the plan (how far to look ahead when finding scheduled maintenance jobs to generate work for).</span></span>
1. <span data-ttu-id="dfa8e-152">Imposta l'opzione **Crea automaticamente un ordine di lavoro dalla pianificazione** su *Sì*.</span><span class="sxs-lookup"><span data-stu-id="dfa8e-152">Set the **Automatically create work order from schedule** option to *Yes*.</span></span>
1. <span data-ttu-id="dfa8e-153">Nella sezione **Ordine di lavoro** seleziona una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="dfa8e-153">In the **Work order** section, select one of the following options:</span></span>

    - <span data-ttu-id="dfa8e-154">**Un ordine di lavoro per riga** - Crea un ordine di lavoro per riga del programma di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="dfa8e-154">**One work order per line** – Create one work order per maintenance schedule line.</span></span> <span data-ttu-id="dfa8e-155">Questa opzione fornisce la stessa funzionalità disponibile quando la funzionalità *Applica le regole per il raggruppamento degli ordini di lavoro durante l'esecuzione di un piano di manutenzione* è disattivata.</span><span class="sxs-lookup"><span data-stu-id="dfa8e-155">(This option provides the same functionality that is available when the *Apply rules for grouping work orders while running a maintenance plan* feature is turned off.)</span></span>
    - <span data-ttu-id="dfa8e-156">**Un ordine di lavoro per** - Crea ordini di lavoro raggruppati in base alle impostazioni delle altre opzioni che diventano disponibili quando selezioni questa opzione.</span><span class="sxs-lookup"><span data-stu-id="dfa8e-156">**One work order per** – Create work orders that are grouped according to the settings of the other options that become available when you select this option.</span></span>

1. <span data-ttu-id="dfa8e-157">Se desideri che le opzioni vengano applicate quando esegui solo alcuni dei tuoi piani di manutenzione, nella Scheda dettaglio **Record da includere** aggiungi i filtri in base alle tue esigenze, proprio come faresti per altri processi batch in Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="dfa8e-157">If you want the options to apply when you run only some of your maintenance plans, on the **Records to include** FastTab, add filters as you require, just as you might do for other batch jobs in Microsoft Dynamics 365 Supply Chain Management.</span></span>
1. <span data-ttu-id="dfa8e-158">Nella Scheda dettaglio **Esegui in background**, configura le opzioni batch e di pianificazione in base alle tue esigenze, proprio come faresti per altri processi batch in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="dfa8e-158">On the **Run in the background** FastTab, set up batch and scheduling options as you require, just as you might do for other batch jobs in Supply Chain Management.</span></span>
1. <span data-ttu-id="dfa8e-159">Seleziona **OK** per eseguire e/o pianificare i piani di manutenzione selezionati.</span><span class="sxs-lookup"><span data-stu-id="dfa8e-159">Select **OK** to run and/or schedule the selected maintenance plans.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]