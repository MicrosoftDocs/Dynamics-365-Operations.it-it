---
title: Cicli di manutenzione
description: In questo argomento vengono descritti i cicli di manutenzione in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetRoundTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: a3a64593a2155d35e78b0d854c7367fa65d1c5c8
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2021
ms.locfileid: "5018548"
---
# <a name="maintenance-rounds"></a><span data-ttu-id="0ae85-103">Cicli di manutenzione</span><span class="sxs-lookup"><span data-stu-id="0ae85-103">Maintenance rounds</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="0ae85-104">In **Gestione cespiti**, è possibile creare cicli di manutenzione per vari cespiti in cui è necessario eseguire un'attività simile a intervalli regolari.</span><span class="sxs-lookup"><span data-stu-id="0ae85-104">In **Asset Management**, you can create maintenance rounds for various assets, on which you need to carry out a similar task at regular intervals.</span></span> <span data-ttu-id="0ae85-105">Ad esempio, le lubrificazioni o le ispezioni di sicurezza da eseguire su una serie di macchine entro gli stessi intervalli.</span><span class="sxs-lookup"><span data-stu-id="0ae85-105">For example, lubrication jobs or safety inspection jobs that need to be carried out on a number of machines within the same intervals.</span></span> <span data-ttu-id="0ae85-106">Il primo passo è di creare un ciclo di manutenzione per i cespiti che richiedono lo stesso tipo di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="0ae85-106">First step is to create a maintenance round, including assets that require the same form of maintenance job.</span></span> <span data-ttu-id="0ae85-107">Successivamente, si programmano i cicli di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="0ae85-107">Next, you schedule the maintenance rounds.</span></span> <span data-ttu-id="0ae85-108">Una volta completata la programmazione dei cicli di manutenzione, è possibile visualizzare tutti i record relativi al ciclo in **Tutti i programmi di manutenzione** e **Apri righe di programma di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="0ae85-108">When you have completed the maintenance rounds schedule, you can see all the job records relating to the round in the **All maintenance schedule** and **Open maintenance schedule lines**.</span></span>

>[!NOTE]
><span data-ttu-id="0ae85-109">I cicli di manutenzione possono anche essere impostati nelle unità funzionali per essere completati nei cespiti installati nell'unità funzionale al momento della creazione dell'ordine di lavoro basato sul ciclo.</span><span class="sxs-lookup"><span data-stu-id="0ae85-109">Maintenance rounds can also be set up on functional locations to be completed on the assets installed on the functional location at the time of creation of the round-based work order.</span></span> <span data-ttu-id="0ae85-110">Per ulteriori informazioni sull'impostazione dei cicli di manutenzione nelle unità funzionali, vedere [Creare unità funzionali](../functional-locations/create-functional-locations.md).</span><span class="sxs-lookup"><span data-stu-id="0ae85-110">Refer to [Create functional locations](../functional-locations/create-functional-locations.md) for more information on the setup of maintenance rounds on functional locations.</span></span>

## <a name="set-up-a-maintenance-round"></a><span data-ttu-id="0ae85-111">Impostare un ciclo di manutenzione</span><span class="sxs-lookup"><span data-stu-id="0ae85-111">Set up a maintenance round</span></span>

1. <span data-ttu-id="0ae85-112">Fare clic su **Gestione cespiti** > **Impostazione** > **Manutenzione preventiva** > **Cicli di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="0ae85-112">Click **Asset management** > **Setup** > **Preventive maintenance** > **Maintenance rounds**.</span></span>

2. <span data-ttu-id="0ae85-113">Fare clic su **Nuovo** per creare un nuovo ciclo di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="0ae85-113">Click **New** to create a new maintenance round.</span></span>

3. <span data-ttu-id="0ae85-114">Immettere un ID nel campo **Ciclo di manutenzione** e un nome per il ciclo nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="0ae85-114">Insert and ID in the **Maintenance round** field, and a name for the maintenance round in the **Name** field.</span></span>

4. <span data-ttu-id="0ae85-115">Selezionare una data di inizio per il ciclo nel campo **Data di inizio**.</span><span class="sxs-lookup"><span data-stu-id="0ae85-115">Select a start date for the round in the **Start date** field.</span></span>

5. <span data-ttu-id="0ae85-116">Nei campi **Termina entro giorni** e **Termina entro ore**, è possibile immettere la data di fine prevista in giorni o ore.</span><span class="sxs-lookup"><span data-stu-id="0ae85-116">In the **Finish within days** and **Finish within hours** fields, you can insert expected end date in days or hours.</span></span> <span data-ttu-id="0ae85-117">La data di fine prevista viene calcolata in relazione alla data di inizio, che viene calcolata alla creazione delle righe di programma di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="0ae85-117">The expected end date is calculated relative to the start date, which is calculated when maintenance schedule lines are created.</span></span> <span data-ttu-id="0ae85-118">Ad esempio, è possibile immettere "7 "nel campo **Termina entro giorni** per indicare che il processo correlato deve essere completato entro una settimana dalla data di inizio.</span><span class="sxs-lookup"><span data-stu-id="0ae85-118">For example, you can insert "7" in the **Finish within days** field to indicate that the related job should be completed within a week from the start date.</span></span>

6. <span data-ttu-id="0ae85-119">Impostare l'interruttore **Crea automaticamente** su "Sì" se gli ordini di lavoro devono essere creati automaticamente dalle righe di programma di manutenzione generate sulla base di questo ciclo di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="0ae85-119">Select "Yes" on the **Auto create** toggle button if work orders should automatically be created from maintenance schedule lines that are created from this maintenance round.</span></span>

7. <span data-ttu-id="0ae85-120">Nel campo **Tipo di ordine di lavoro**, selezionare il tipo di ordine di lavoro da utilizzare negli ordini di lavoro creati da questo ciclo di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="0ae85-120">In the **Work order type** field, select the work order type to be used on work orders created from this maintenance round.</span></span>

8. <span data-ttu-id="0ae85-121">Nel campo **Livello servizio**, selezionare il livello di servizio di ordine di lavoro da utilizzare negli ordini di lavoro creati da questo ciclo di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="0ae85-121">In the **Service level** field, select the work order service level to be used on work orders created from this maintenance round.</span></span>

9. <span data-ttu-id="0ae85-122">Nella Scheda dettaglio **Righe cespite**, fare clic su **Aggiungi** per aggiungere un cespite al ciclo di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="0ae85-122">On the **Asset lines** FastTab, click **Add** to add an asset to the maintenance round.</span></span>

10. <span data-ttu-id="0ae85-123">Un numero di riga viene automaticamente inserito nel campo **Numero riga** per indicare la sequenza dei cespiti nel ciclo di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="0ae85-123">A line number is automatically inserted in the **Line number** field to indicate the sequence of the assets in maintenance round.</span></span>

11. <span data-ttu-id="0ae85-124">Selezionare il cespite nel campo **Cespite**.</span><span class="sxs-lookup"><span data-stu-id="0ae85-124">Select the asset in the **Asset** field.</span></span>

12. <span data-ttu-id="0ae85-125">Selezionare il tipo di processo di manutenzione per il cespite nel campo **Tipo di processo di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="0ae85-125">Select the maintenance job type for the asset in the **Maintenance job type** field.</span></span>

13. <span data-ttu-id="0ae85-126">Se necessario, selezionare la **Variante di tipo di processo di manutenzione** e il **Settore** associati al tipo di processo di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="0ae85-126">If required, select **Maintenance job typ variant** and **Trade** related to the maintenance job type.</span></span>

14. <span data-ttu-id="0ae85-127">Selezionare la ricorrenza (giorno, settimana e così via.) nel campo **Tipo di periodo**.</span><span class="sxs-lookup"><span data-stu-id="0ae85-127">Select the recurrence (day, week, etc.) in the **Period type** field.</span></span>

15. <span data-ttu-id="0ae85-128">Nel campo **Frequenza periodo**, immettere il numero di ricorrenze per il ciclo di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="0ae85-128">In the **Period frequency** field, insert the number of recurrences for the maintenance round.</span></span> <span data-ttu-id="0ae85-129">Esempio: se è stato selezionato "Giorno" nel campo **Tipo di periodo** e si immette "7" in questo campo, le righe del ciclo di manutenzione vengono create una volta alla settimana durante la programmazione della manutenzione preventiva.</span><span class="sxs-lookup"><span data-stu-id="0ae85-129">Example: If you have selected "Day" in the **Period type** field, and you insert the number "7" in this field, new maintenance round lines are created during preventive maintenance scheduling once a week.</span></span>

16. <span data-ttu-id="0ae85-130">Selezionare una data di inizio per il cespite da includere nel ciclo di manutenzione nel campo **Data di inizio**.</span><span class="sxs-lookup"><span data-stu-id="0ae85-130">Select a start date for the asset to be included in the maintenance round in the **Start date** field.</span></span> <span data-ttu-id="0ae85-131">Questa data può differire da quella impostata nel ciclo di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="0ae85-131">This date may differ from the start date set on the maintenance round.</span></span>

17. <span data-ttu-id="0ae85-132">Ripetere i passaggi da 9 a 16 per aggiungere ulteriori cespiti al ciclo di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="0ae85-132">Repeat steps 9-16 to add more assets to the maintenance round.</span></span>

18. <span data-ttu-id="0ae85-133">Nella Scheda dettaglio **Righe unità funzionale**, fare clic su **Aggiungi** per aggiungere un'unità funzionale al ciclo di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="0ae85-133">On the **Functional location lines** FastTab, click **Add** to add a functional location to the maintenance round.</span></span> <span data-ttu-id="0ae85-134">Fare riferimento alla descrizione dei campi correlati visti nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="0ae85-134">Refer to the description of the related fields above.</span></span> <span data-ttu-id="0ae85-135">Gli stessi campi sono disponibili per la creazione di una riga di cespite, ma è anche possibile selezionare **Produttore** e **Modello** per un'unità funzionale, se necessario.</span><span class="sxs-lookup"><span data-stu-id="0ae85-135">The same fields are available as for creating an asset line, but you can also select **Manufacturer** and **Model** for a functional location, if required.</span></span> <span data-ttu-id="0ae85-136">Se si seleziona solo un'unità funzionale in una riga, ma non si effettuano selezioni in **Tipo di cespite**, **Produttore**, **Modello**, **Tipo di processo di manutenzione**, **Variante tipi di processo di manutenzione** e **Settore**, tutti i cespiti associati a quell'unità funzionale al momento della programmazione di manutenzione verranno inclusi nel ciclo di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="0ae85-136">If you only select a functional location on a line, but make no selections in **Asset type**, **Manufacturer**, **Model**, **Maintenance job type**, **Maintenance job type variant** and **Trade**, all assets related to that functional location at the time of maintenance scheduling will be included in the maintenance round.</span></span>

19. <span data-ttu-id="0ae85-137">Nella Scheda dettaglio **Pool**, fare clic su **Aggiungi** per selezionare un pool di ordini di da includere nel ciclo di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="0ae85-137">On the **Pools** FastTab, click **Add** to select a work order pool to be included in the maintenance round.</span></span> <span data-ttu-id="0ae85-138">È possibile collegare vari pool di ordini di lavoro a un ciclo di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="0ae85-138">Several work order pools can be connected to one maintenance round.</span></span>

20. <span data-ttu-id="0ae85-139">Salvare l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="0ae85-139">Save your setup.</span></span>

>[!NOTE]
><span data-ttu-id="0ae85-140">I campi **Cespiti** e **Righe** nel gruppo **Dettagli** della Scheda dettaglio **Intestazione** indicano il numero totale di cespiti e righe associati al ciclo di manutenzione selezionato.</span><span class="sxs-lookup"><span data-stu-id="0ae85-140">The **Assets** and **Lines** fields located in the **Details** group on the **Header** FastTab show the total number of assets and lines related to the selected maintenance round.</span></span>

<span data-ttu-id="0ae85-141">L'illustrazione seguente mostra ed esempio di un ciclo di manutenzione contenente tre cespiti.</span><span class="sxs-lookup"><span data-stu-id="0ae85-141">The illustration below shows and example of a maintenance round containing three assets.</span></span>

![Figura 1](media/13-preventive-maintenance.png)


## <a name="schedule-maintenance-rounds"></a><span data-ttu-id="0ae85-143">Programma cicli di manutenzione</span><span class="sxs-lookup"><span data-stu-id="0ae85-143">Schedule maintenance rounds</span></span>

<span data-ttu-id="0ae85-144">Dopo l'impostazione di un ciclo di manutenzione, si esegue un processo di programmazione per programmare tutti i processi correlati al ciclo di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="0ae85-144">When you've set up a maintenance round, you run a schedule job to schedule all the jobs related to the maintenance round.</span></span>

1. <span data-ttu-id="0ae85-145">Fare clic su **Gestione cespiti** > **Periodico** > **Manutenzione preventiva** > ,**Programma cicli di manutenzione** o **Gestione cespiti** > **Comune** > **Programma di manutenzione** > **Tutti i programmi di manutenzione** o **Apri righe di programma di manutenzione** o **Apro pool di programmi di manutenzione** > selezionare la riga di programma di manutenzione nell'elenco > pulsante **Cicli di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="0ae85-145">Click **Asset management** > **Periodic** > **Preventive maintenance** > **Schedule maintenance rounds**, or **Asset management** > **Common** > **Maintenance schedule** > **All maintenance schedule** or **Open maintenance schedule lines** or **Open maintenance schedule pools** > select maintenance schedule line in the list > **Maintenance rounds** button.</span></span>

2. <span data-ttu-id="0ae85-146">Nel campo **Periodo**, selezionare il tipo di periodo da utilizzare per il processo di programmazione.</span><span class="sxs-lookup"><span data-stu-id="0ae85-146">In the **Period** field, select the period type to be used for the scheduling job.</span></span>

3. <span data-ttu-id="0ae85-147">Nel campo **Frequenza periodo**, inserire il numero di periodi da includere nel processo di programmazione.</span><span class="sxs-lookup"><span data-stu-id="0ae85-147">In the **Period frequency** field, insert the number of periods to be included in the scheduling job.</span></span> <span data-ttu-id="0ae85-148">L'inizio della programmazione è la data corrente.</span><span class="sxs-lookup"><span data-stu-id="0ae85-148">The start of the scheduling is the current date.</span></span>

4. <span data-ttu-id="0ae85-149">Impostare l'interruttore **Crea automaticamente** su "Sì" se un ordine di lavoro deve essere creato automaticamente in base al ciclo di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="0ae85-149">Select "Yes" on the **Auto create** toggle button if a work order should automatically be created on the basis of a maintenance round.</span></span>

>[!NOTE]
><span data-ttu-id="0ae85-150">Se questo interruttore è impostato su "Sì" e anche l'interruttore **Crea automaticamente** è impostato su "Sì" nel ciclo di manutenzione nel modulo **Cicli di manutenzione**, gli ordini di lavoro sono creati in base alle righe del ciclo di manutenzione e vengono create anche le righe di programma di manutenzione con lo stato "Ordine di lavoro creato".</span><span class="sxs-lookup"><span data-stu-id="0ae85-150">If this toggle button is set to "Yes", and the **Auto create** toggle button is also set to "Yes" on the maintenance round in **Maintenance rounds** form, work orders are created based on the maintenance round lines, and maintenance schedule lines with status "Work order created" are also created.</span></span> <span data-ttu-id="0ae85-151">Se solo uno degli interruttori **Crea automaticamente** è impostato su "Sì", in questo elenco a discesa o in **Cicli di manutenzione**, solo le righe di programma di manutenzione vengono create con lo stato "Creata".</span><span class="sxs-lookup"><span data-stu-id="0ae85-151">If only one of the **Auto create** toggle buttons is set to "Yes", in this drop-down or in **Maintenance rounds**, only maintenance schedule lines are created with status "Created".</span></span> <span data-ttu-id="0ae85-152">In tal caso, non viene creato alcun ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0ae85-152">In that case, no work orders are created.</span></span>

5. <span data-ttu-id="0ae85-153">Se necessario, è possibile selezionare specifici cicli o un'altra data di inizio per il processo di programmazione.</span><span class="sxs-lookup"><span data-stu-id="0ae85-153">If required, you can select specific rounds or another start date for the schedule job.</span></span> <span data-ttu-id="0ae85-154">Fare clic su **Filtro** e aggiungere i cicli da includere.</span><span class="sxs-lookup"><span data-stu-id="0ae85-154">Click **Filter**, and add the rounds to be included.</span></span>

6. <span data-ttu-id="0ae85-155">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0ae85-155">Click **OK**.</span></span>

7. <span data-ttu-id="0ae85-156">A questo punto è possibile visualizzare i processi dei cicli di manutenzione in **Gestione cespiti** > **Comune** > **Programma di manutenzione** > **Tutti i programmi di manutenzione** o **Apri righe di programma di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="0ae85-156">You are now able to see the maintenance rounds jobs in **Asset management** > **Common** > **Maintenance schedule** > **All maintenance schedule** or **Open maintenance schedule lines**.</span></span> <span data-ttu-id="0ae85-157">Se i cicli di manutenzione sono collegati a un pool di ordini di lavoro, vengono visualizzate anche le righe di programma di manutenzione in **Apri pool di programmazione di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="0ae85-157">If the scheduled rounds are connected to a work order pool, you also see maintenance schedule lines in **Open maintenance schedule pools**.</span></span> <span data-ttu-id="0ae85-158">Le righe di programma di manutenzione create da un ciclo hanno il tipo di riferimento "Cicli di manutenzione".</span><span class="sxs-lookup"><span data-stu-id="0ae85-158">Maintenance schedule lines created from a round have the reference type "Maintenance rounds".</span></span>

<span data-ttu-id="0ae85-159">Le due illustrazioni di seguito illustrano un processo di programmazione nella finestra di dialogo **Cicli di programmazione della manutenzione** e le righe del programma di manutenzione create in **Tutto il programma di manutenzione** in base al processo di programmazione.</span><span class="sxs-lookup"><span data-stu-id="0ae85-159">The two illustrations below show a schedule job in the **Schedule maintenance rounds** dialog, and the maintenance schedule lines created in **All maintenance schedule** based on that schedule job.</span></span>

![Figura 2](media/14-preventive-maintenance.png)

![Figura 3](media/15-preventive-maintenance.png)

- <span data-ttu-id="0ae85-162">Quando gli ordini di lavoro vengono creati manualmente nei cespiti coperti da un garanzia fornitore, viene visualizzata una finestra di dialogo per informare l'utente della garanzia.</span><span class="sxs-lookup"><span data-stu-id="0ae85-162">When work orders are manually created on assets that are covered by a vendor warranty, a dialog box is shown to make the user aware of the warranty.</span></span> <span data-ttu-id="0ae85-163">La creazione dell'ordine di lavoro può quindi essere annullata.</span><span class="sxs-lookup"><span data-stu-id="0ae85-163">The creation of the work order can then be canceled.</span></span> <span data-ttu-id="0ae85-164">La verifica di una relazione di garanzia viene omessa per gli ordini di lavoro creati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0ae85-164">The check for a warranty relation is omitted for work orders that are automatically created.</span></span>  
- <span data-ttu-id="0ae85-165">È possibile impostare un processo batch nella Scheda dettaglio **Esecuzione in background** per programmare i cicli a intervalli regolari.</span><span class="sxs-lookup"><span data-stu-id="0ae85-165">You can set up a batch job on the **Run in the background** FastTab to schedule rounds at regular intervals.</span></span>  
- <span data-ttu-id="0ae85-166">Se un ciclo è incluso in vari pool di ordini di lavoro (vedere [Pool di ordini di lavoro](../work-orders/work-order-pools.md)), un record viene visualizzato per ogni pool in **Apri pool di programmi di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="0ae85-166">If a round is included in several work order pools (refer to [Work order pools](../work-orders/work-order-pools.md)), one record is shown for each pool in **Open maintenance schedule pools**.</span></span> <span data-ttu-id="0ae85-167">Questa operazione viene eseguita per ottimizzare le opzioni di filtro per i pool di ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0ae85-167">This is done to optimize the filtering options for work order pools.</span></span>

