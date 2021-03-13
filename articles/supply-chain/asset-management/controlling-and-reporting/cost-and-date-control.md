---
title: Controllo dei costi e delle date
description: In questo argomento viene descritto il controllo dei costi e delle date in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetBICostControlWorkspace, EntAssetWorkOrderDateControl, EntAssetWorkOrderForecastCostInfoPart, EntAssetMaintenanceCostTrans, EntAssetWorkOrderDateControlCalcDialog, EntAssetCostControl, EntAssetCostObjectCalendar, EntAssetWorkOrderCostInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1de12233ff296f77ba9984fa8d957d4c2bc90b3f
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2021
ms.locfileid: "5019077"
---
# <a name="cost-and-date-control"></a><span data-ttu-id="22d59-103">Controllo dei costi e delle date</span><span class="sxs-lookup"><span data-stu-id="22d59-103">Cost and date control</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="22d59-104">In Gestione cespiti, è possibile calcolare i costi per ottenere una panoramica dei costi effettivi comparati ai costi in budget in cespiti, unità funzionali e ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="22d59-104">In Asset Management, you can calculate costs to get an overview of actual costs compared to budget costs on assets, functional locations, and work orders.</span></span> <span data-ttu-id="22d59-105">I costi effettivi sono basati sulle transazioni registrate.</span><span class="sxs-lookup"><span data-stu-id="22d59-105">Actual costs are based on posted transactions.</span></span> 

<span data-ttu-id="22d59-106">È inoltre possibile eseguire un calcolo delle date se si desidera confrontare le date di inizio e fine programmate alle date di inizio e di fine effettive negli ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="22d59-106">You can also make a date calculation if you want to compare scheduled start and end dates to actual start and end dates on work orders.</span></span>

## <a name="cost-control-for-assets-functional-locations-and-work-orders"></a><span data-ttu-id="22d59-107">Controllo dei costi per cespiti, unità funzionali e ordini di lavoro</span><span class="sxs-lookup"><span data-stu-id="22d59-107">Cost control for assets, functional locations, and work orders</span></span>

<span data-ttu-id="22d59-108">I calcoli effettuati per cespiti, aree funzionali e ordini di lavoro sono quasi identici.</span><span class="sxs-lookup"><span data-stu-id="22d59-108">The calculations made for assets, functional locations, and work orders are almost identical.</span></span> <span data-ttu-id="22d59-109">L'unica differenza è che per i cespiti e le unità funzionali, è possibile includere cespiti secondari e ubicazioni secondarie nel calcolo.</span><span class="sxs-lookup"><span data-stu-id="22d59-109">The only difference is that for assets and functional locations, you can also include sub assets and sub locations in your calculation.</span></span> <span data-ttu-id="22d59-110">La data è quella di transazione alla quale la registrazione è stata registrata.</span><span class="sxs-lookup"><span data-stu-id="22d59-110">The date is the transaction date when the registration was recorded.</span></span>

1. <span data-ttu-id="22d59-111">Fare clic su **Gestione cespiti** > **Richieste di informazioni** > **Cespiti** > **Controllo costi cespiti** o **Controllo costi unità funzionali** o **Gestione cespiti** > **Richieste di informazioni** > **Ordini di lavoro** > **Controllo costi ordini di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="22d59-111">Click **Asset management** > **Inquiries** > **Assets** > **Asset cost control** or **Functional location cost control**, or **Asset management** > **Inquiries** > **Work orders** > **Work order cost control**.</span></span>

2. <span data-ttu-id="22d59-112">Nella finestra di dialogo **Controllo costi cespiti** / **Controllo costi unità funzionali** / **Controllo costi ordini di lavoro**, selezionare un intervallo di tempo da calcolare.</span><span class="sxs-lookup"><span data-stu-id="22d59-112">In the **Asset cost control** / **Functional location cost control** / **Work order cost control** dialog, select a time range to be calculated.</span></span>

3. <span data-ttu-id="22d59-113">Se necessario, selezionare un set di dimensioni finanziarie da includere nel calcolo.</span><span class="sxs-lookup"><span data-stu-id="22d59-113">If required, select a financial dimension set to be included in the calculation.</span></span>

4. <span data-ttu-id="22d59-114">Impostare l'interruttore **Ignora lo zero** su "Sì" se non si desidera visualizzare i risultati con un costo zero.</span><span class="sxs-lookup"><span data-stu-id="22d59-114">Select "Yes" on the **Skip zero** toggle button if you don't want to show results with a cost of zero.</span></span>

5. <span data-ttu-id="22d59-115">È possibile utilizzare il campo **Livello** per indicare il livello di dettagli delle righe del controllo dei costi in relazione alle unità funzionali.</span><span class="sxs-lookup"><span data-stu-id="22d59-115">You can use the **Level** field to indicate how detailed you want the cost control lines to be regarding functional locations.</span></span> 

    <span data-ttu-id="22d59-116">Ad esempio, se si inserisce "1" nel campo e si ha una gerarchia di unità funzionali multilivello, tutte le righe di controllo dei costi di un'unità funzionale verranno visualizzate nel livello principale, quindi le ore in una riga possono essere aggiunte dalle unità funzionali situate a un livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="22d59-116">For example, if you insert the number "1" in the field, and you have a multi-level functional location hierarchy, all cost control lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> 
    
    <span data-ttu-id="22d59-117">Se si inserisce "0" nel campo **Livello**, verrà visualizzato un risultato dettagliato che mostra tutte le righe del controllo dei costi in tutti i livelli di unità funzionali a cui sono correlate.</span><span class="sxs-lookup"><span data-stu-id="22d59-117">If you insert the number "0" in the **Level** field, you will see a detailed result showing all cost control lines on all the functional location level to which they are related.</span></span>

6. <span data-ttu-id="22d59-118">Impostare l'interruttore **Mostra costo impegnato aperto** su "Sì" se si desidera includere quella colonna nel calcolo.</span><span class="sxs-lookup"><span data-stu-id="22d59-118">Select "Yes" on the **Show open committed cost** toggle button if you want to include that column in the calculation.</span></span>

7. <span data-ttu-id="22d59-119">Impostare l'interruttore **Includere cespiti secondari** su "Sì" per visualizzare i costi correlati ai cespiti secondari come righe separate.</span><span class="sxs-lookup"><span data-stu-id="22d59-119">Select "Yes" on the **Include sub assets** toggle button to show costs related to sub assets as separate lines.</span></span>

8. <span data-ttu-id="22d59-120">Se si desidera limitare la ricerca, è possibile selezionare specifici cespiti/unità funzionali/ordini di lavoro nella Scheda dettaglio **Record da includere**.</span><span class="sxs-lookup"><span data-stu-id="22d59-120">If you want to limit the search, you can select specific assets / functional locations / work orders on the **Records to include** FastTab.</span></span>

9. <span data-ttu-id="22d59-121">Fare clic su **OK** per avviare il calcolo.</span><span class="sxs-lookup"><span data-stu-id="22d59-121">Click **OK** to start the calculation.</span></span>

    <span data-ttu-id="22d59-122">Nella figura seguente viene illustrato un esempio della finestra di dialogo **Controllo costi cespiti**.</span><span class="sxs-lookup"><span data-stu-id="22d59-122">The figure below shows an example of the **Asset cost control** dialog.</span></span>

    ![Finestra di dialogo Controllo costi cespiti](media/01-controlling-and-reporting.png)

10. <span data-ttu-id="22d59-124">Nella pagina **Controllo costi cespiti**, fare clic sul pulsante **Raggruppa per** per visualizzare il livello di dettagli necessario per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="22d59-124">On the **Asset cost control** page, click the **Group by** buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="22d59-125">I pulsanti **Raggruppa per** selezionati sono evidenziati.</span><span class="sxs-lookup"><span data-stu-id="22d59-125">The selected **Group by** buttons are highlighted.</span></span> <span data-ttu-id="22d59-126">Fare clic su un pulsante per attivarlo o disattivarlo.</span><span class="sxs-lookup"><span data-stu-id="22d59-126">Click on a button to activate or deactivate it.</span></span>

## <a name="example"></a><span data-ttu-id="22d59-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="22d59-127">Example</span></span>

<span data-ttu-id="22d59-128">Nella schermata seguente viene illustrato un esempio di risultati di calcolo in **Controllo costi cespiti**.</span><span class="sxs-lookup"><span data-stu-id="22d59-128">The screenshot below shows an example of calculation results in **Asset cost control**.</span></span>

- <span data-ttu-id="22d59-129">Nel campo **Budget originale** sono visualizzati i costi in budget della previsione dell'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="22d59-129">The **Original budget** field shows budget costs from the work order forecast.</span></span> 
- <span data-ttu-id="22d59-130">Il campo **Costo impegnato** mostra l'importo totale delle spese che una persona giuridica si è impegnata a pagare.</span><span class="sxs-lookup"><span data-stu-id="22d59-130">The **Committed cost** field shows the total amount of expenses that a legal entity has committed itself to pay.</span></span> 
- <span data-ttu-id="22d59-131">Nel campo **Costo impegnato aperto** sono visualizzati gli impegni per il pagamento di articoli, ore e servizi ordinati o ricevuti ma non ancora pagati.</span><span class="sxs-lookup"><span data-stu-id="22d59-131">The **Open committed cost** field shows commitments to pay for items, hours, and services you have ordered or received but not yet paid for.</span></span> 
- <span data-ttu-id="22d59-132">Dopo che tutte le registrazioni del consumo sono state registrate, i costi correlati vengono mostrati nel campo **Costo effettivo**.</span><span class="sxs-lookup"><span data-stu-id="22d59-132">The **Actual cost** field shows related costs after all consumption registrations have been posted.</span></span>

![Esempio di risultati del calcolo in Controllo costi cespiti](media/02-controlling-and-reporting.png)

<span data-ttu-id="22d59-134">Un altro metodo di eseguire un calcolo dei costi è la selezione di molteplici cespiti in **Tutti i cespiti** o **Cespiti attivi**.</span><span class="sxs-lookup"><span data-stu-id="22d59-134">Another way of making a cost calculation is to multi-select assets in **All assets** or **Active assets**.</span></span> <span data-ttu-id="22d59-135">Quindi, fare clic sul pulsante **Controllo costi** nella scheda **Generale**. Nella finestra di dialogo **Controllo costi cespiti**, i cespiti selezionati vengono inseriti automaticamente nel campo **Cespite** della Scheda dettaglio **Record da includere**.</span><span class="sxs-lookup"><span data-stu-id="22d59-135">Then, you click the **Cost control** button on the **General** tab. In the **Asset cost control** dialog, the selected assets are automatically inserted in the **Asset** field on the **Records to include** FastTab.</span></span> <span data-ttu-id="22d59-136">Fare clic **OK**. Viene visualizzato un calcolo dei costi per i cespiti selezionati.</span><span class="sxs-lookup"><span data-stu-id="22d59-136">Click **OK**, and a cost calculation for the selected assets is shown.</span></span> <span data-ttu-id="22d59-137">La stessa procedura può essere eseguita per le unità funzionali in **Tutte le unità funzionali** o **Unità funzionali attive** e per gli ordini di lavoro in **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.</span><span class="sxs-lookup"><span data-stu-id="22d59-137">The same procedure can be done for functional locations in **All functional locations** or **Active functional locations**, and for work orders in **All work orders** or **Active work orders**.</span></span>


## <a name="work-order-date-control"></a><span data-ttu-id="22d59-138">Controllo data dell'ordine di lavoro</span><span class="sxs-lookup"><span data-stu-id="22d59-138">Work order date control</span></span>

<span data-ttu-id="22d59-139">Utilizzare questa pagina per ottenere una panoramica delle date di inizio e di fine previste comparate alle date di inizio e di fine negli ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="22d59-139">Use this page to get an overview of expected start and end dates compared to actual start and end dates on work orders.</span></span>

1. <span data-ttu-id="22d59-140">Fare clic su **Gestione cespiti** > **Richieste di informazioni** > **Ordini di lavoro** > **Controllo date ordini di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="22d59-140">Click **Asset management** > **Inquiries** > **Work orders** > **Work order date control**.</span></span>

2. <span data-ttu-id="22d59-141">Fare clic su **Calcola**.</span><span class="sxs-lookup"><span data-stu-id="22d59-141">Click **Calculate**.</span></span>

3. <span data-ttu-id="22d59-142">Selezionare un'unità funzionale nel campo **Unità funzionale**.</span><span class="sxs-lookup"><span data-stu-id="22d59-142">Select a functional location in the **Functional location** field.</span></span>

4. <span data-ttu-id="22d59-143">Inserire l'intervallo per il quale si desidera eseguire il calcolo nei campi **Dal** e **Al**.</span><span class="sxs-lookup"><span data-stu-id="22d59-143">Insert the range for which you want to make the calculation in the **From date** and **To date** fields.</span></span> <span data-ttu-id="22d59-144">Verranno inclusi tutti gli ordini di lavoro con la data di inizio prevista compresa nell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="22d59-144">All work orders with expected start date within the range will be included.</span></span>

5. <span data-ttu-id="22d59-145">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="22d59-145">Click **OK**.</span></span>

6. <span data-ttu-id="22d59-146">Fare clic sui pulsanti **Raggruppa per** per visualizzare il livello di dettagli necessario per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="22d59-146">Click the **Group by** buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="22d59-147">I pulsanti **Raggruppa per** selezionati sono evidenziati.</span><span class="sxs-lookup"><span data-stu-id="22d59-147">The selected **Group by** buttons are highlighted.</span></span> <span data-ttu-id="22d59-148">Fare clic su un pulsante per attivarlo o disattivarlo.</span><span class="sxs-lookup"><span data-stu-id="22d59-148">Click on a button to activate or deactivate it.</span></span>

## <a name="example"></a><span data-ttu-id="22d59-149">Esempio</span><span class="sxs-lookup"><span data-stu-id="22d59-149">Example</span></span>

<span data-ttu-id="22d59-150">Nella schermata seguente viene illustrato un esempio di risultati di calcolo in **Controllo date ordini di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="22d59-150">The screenshot below shows an example of calculation results in **Work order date control**.</span></span>

- <span data-ttu-id="22d59-151">Il campo **Ritardo inizio medio** visualizza la differenza in giorni tra la data di inizio programmata per un ordine di lavoro rispetto alla data di inizio effettiva.</span><span class="sxs-lookup"><span data-stu-id="22d59-151">The **Avg. start delay** field shows the difference in days between scheduled start date for a work order compared to actual start date.</span></span> <span data-ttu-id="22d59-152">Se, ad esempio, la data di inizio effettiva è due giorni prima la data di inizio programmata, in questo campo viene visualizzato "- 2".</span><span class="sxs-lookup"><span data-stu-id="22d59-152">If, for example, the actual start date was two days before the scheduled start date, "-2" will be displayed in this field.</span></span>  
- <span data-ttu-id="22d59-153">Il campo **Ritardo fine medio** visualizza la differenza in giorni tra la data di fine programmata per un ordine di lavoro rispetto alla data di fine effettiva.</span><span class="sxs-lookup"><span data-stu-id="22d59-153">The **Avg. end delay** field shows the difference in days between scheduled end date for a work order compared to actual end date.</span></span> <span data-ttu-id="22d59-154">Se, ad esempio, la data di fine effettiva è tre giorni dopo la data di fine programmata, in questo campo viene visualizzato "3".</span><span class="sxs-lookup"><span data-stu-id="22d59-154">If, for example, the actual end date was three days after the scheduled end date, "3" will be displayed in this field.</span></span>  
- <span data-ttu-id="22d59-155">I campi **Occorrenze** mostrano il numero di scostamenti in relazione alla data di inizio programmata ed effettiva e alla data di fine programmata ed effettiva nell'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="22d59-155">The **Occurrences** fields show the number of times deviations occur in relation to scheduled and actual start date, and scheduled and actual end date on the work order.</span></span>

![Esempio di risultati del calcolo in Controllo data dell'ordine di lavoro](media/03-controlling-and-reporting.png)


