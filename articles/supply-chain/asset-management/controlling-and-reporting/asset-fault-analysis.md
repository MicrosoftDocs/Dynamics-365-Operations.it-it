---
title: Analisi degli errori dei cespiti
description: In questo argomento viene descritta l'analisi degli errori di cespite in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectFaultCalculate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e911f7ca3b67acd9d5a1b170d8c99135da730847
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2020
ms.locfileid: "3889148"
---
# <a name="asset-fault-analysis"></a><span data-ttu-id="d1547-103">Analisi degli errori dei cespiti</span><span class="sxs-lookup"><span data-stu-id="d1547-103">Asset fault analysis</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="d1547-104">In Gestione cespiti, è possibile analizzare le registrazioni di errore di cespite per ottenere una panoramica del numero totale di errori registrati durante un periodo specifico.</span><span class="sxs-lookup"><span data-stu-id="d1547-104">In Asset Management, you can analyze asset fault registrations to get an overview of the total number of faults registered during a specific period.</span></span> <span data-ttu-id="d1547-105">Le registrazioni di errore possono essere analizzate da varie prospettive, ad esempio in relazione cespiti, tipi di cespite, unità funzionali, sintomi di errore o tipi di errore.</span><span class="sxs-lookup"><span data-stu-id="d1547-105">Fault registrations can be analyzed from different perspectives, for example with focus on assets, asset types, functional locations, fault symptoms, or fault types.</span></span>

1. <span data-ttu-id="d1547-106">Fare clic su **Gestione cespiti** > **Richieste di informazioni** > **Errore di cespite** > **Analisi degli errori dei cespiti**.</span><span class="sxs-lookup"><span data-stu-id="d1547-106">Click **Asset management** > **Inquiries** > **Asset fault** > **Asset fault analysis**.</span></span>

2. <span data-ttu-id="d1547-107">Nella finestra di dialogo **Calcolo analisi errori dei cespiti**, è possibile utilizzare il campo **Livello** per indicare il livello di dettagli delle righe degli errori di cespite in relazione alle unità funzionali.</span><span class="sxs-lookup"><span data-stu-id="d1547-107">In the **Asset fault analysis calculation** dialog, you can use the **Level** field to indicate how detailed you want the asset fault lines to be regarding functional locations.</span></span> 

    <span data-ttu-id="d1547-108">Ad esempio, se si inserisce "1" nel campo e si ha una struttura di unità funzionali multilivello, tutte le righe degli errori di cespite per un'unità funzionale verranno visualizzate nel livello principale, quindi le ore in una riga possono essere aggiunte dalle unità funzionali situate a un livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="d1547-108">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all asset fault lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> 
        
    <span data-ttu-id="d1547-109">Se si inserisce "0" nel campo **Livello**, verrà visualizzato un risultato dettagliato che mostra tutte le righe degli errori di cespite in tutti i livelli di unità funzionali a cui sono correlate.</span><span class="sxs-lookup"><span data-stu-id="d1547-109">If you insert the number "0" in the **Level** field, you will see a detailed result showing all asset fault lines on all the functional location level to which they are related.</span></span>

3. <span data-ttu-id="d1547-110">Se si desidera limitare la ricerca, è possibile selezionare specifici cespiti, date di errore, cause di errore e rimedi agli errori nella Scheda dettaglio **Record da includere**.</span><span class="sxs-lookup"><span data-stu-id="d1547-110">If you want to limit the search, you can select specific assets, fault dates, fault causes, and fault remedies on the **Records to include** FastTab.</span></span>

4. <span data-ttu-id="d1547-111">Fare clic su **OK** per avviare il calcolo.</span><span class="sxs-lookup"><span data-stu-id="d1547-111">Click **OK** to start the calculation.</span></span>

5. <span data-ttu-id="d1547-112">Nella scheda **Analisi degli errori dei cespiti**, fare clic su uno o più pulsanti **Raggruppa per** per visualizzare il livello di dettagli desiderato.</span><span class="sxs-lookup"><span data-stu-id="d1547-112">On the **Asset fault analysis** tab, click one or more **Group by** buttons to display the detail level you want to see.</span></span> <span data-ttu-id="d1547-113">I pulsanti attivati sono evidenziati.</span><span class="sxs-lookup"><span data-stu-id="d1547-113">Activated buttons are highlighted.</span></span> <span data-ttu-id="d1547-114">Fare clic sui pulsanti per attivarli o disattivarli.</span><span class="sxs-lookup"><span data-stu-id="d1547-114">Activate or deactivate buttons by clicking on them.</span></span>

6. <span data-ttu-id="d1547-115">Fare clic su **Aggiorna calcoli** per visualizzare le selezioni sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="d1547-115">Click **Update calculations** to show your selections on the screen.</span></span> 

>[!NOTE]
><span data-ttu-id="d1547-116">Ogni volta che si attiva o disattiva un pulsante **Raggruppa per**, occorre sempre fare clic sul pulsante **Aggiorna calcoli**.</span><span class="sxs-lookup"><span data-stu-id="d1547-116">Every time you activate or deactivate a **Group by** button, remember to click the **Update calculations** button.</span></span> <span data-ttu-id="d1547-117">Ciò è necessario in quanto una grande quantità di dati viene elaborata durante il ricalcolo della probabilità di errore.</span><span class="sxs-lookup"><span data-stu-id="d1547-117">This is required because a large amount of data is processed as you are recalculating fault probability.</span></span>

## <a name="examples"></a><span data-ttu-id="d1547-118">Esempi</span><span class="sxs-lookup"><span data-stu-id="d1547-118">Examples</span></span>

<span data-ttu-id="d1547-119">Esistono vari modi di analizzare le registrazioni di errore.</span><span class="sxs-lookup"><span data-stu-id="d1547-119">There are many ways to analyze fault registrations.</span></span> <span data-ttu-id="d1547-120">Questa sezione include cinque esempi su come differenti selezioni di dati forniscono più informazioni e dettagli durante l'analisi delle registrazioni di errore di cespite.</span><span class="sxs-lookup"><span data-stu-id="d1547-120">This section has five examples of how different data selections can provide more insight and detail when analyzing asset fault registrations.</span></span>

### <a name="group-by-symptoms"></a><span data-ttu-id="d1547-121">Raggruppare per sintomi</span><span class="sxs-lookup"><span data-stu-id="d1547-121">Group by symptoms</span></span>

<span data-ttu-id="d1547-122">Nel schermata seguente, solo il pulsante **Sintomo** è selezionato.</span><span class="sxs-lookup"><span data-stu-id="d1547-122">In the screenshot below, only the **Symptom** button is selected.</span></span>

- <span data-ttu-id="d1547-123">Le registrazioni di errore sono state effettuate per tre sintomi di errore: "Perdita d'aria", "Fusibile bruciato" e "attrezzatura inceppata".</span><span class="sxs-lookup"><span data-stu-id="d1547-123">Fault registrations have been made on three fault symptoms: "Air leak", "Blown fuse", and "Equipment jammed".</span></span>  
- <span data-ttu-id="d1547-124">Nella colonna **% probabilità**, la somma di tutte le percentuali equivale al 100%.</span><span class="sxs-lookup"><span data-stu-id="d1547-124">In the **Probability %** column, all percentages add up to 100%.</span></span> <span data-ttu-id="d1547-125">La probabilità è basata su tutte le registrazioni di **Sintomi** in questa analisi degli errori.</span><span class="sxs-lookup"><span data-stu-id="d1547-125">Probability is based on all **Symptom** registrations in this fault analysis.</span></span>

![Figura 1](media/06-controlling-and-reporting.png)

### <a name="group-by-symptoms-and-time-period"></a><span data-ttu-id="d1547-127">Raggruppare per sintomi e periodo di tempo</span><span class="sxs-lookup"><span data-stu-id="d1547-127">Group by symptoms and time period</span></span>

<span data-ttu-id="d1547-128">Nella schermata seguente, sono stati aggiunti **Anno** e **Mese** per mostrare come è possibile visualizzare le registrazioni di errore durante un periodo selezionato.</span><span class="sxs-lookup"><span data-stu-id="d1547-128">In the screenshot below, **Year** and **Month** are added to show how you can view fault registrations during a selected period.</span></span>

- <span data-ttu-id="d1547-129">I sintomi di errore sono ora visualizzati come registrazioni per anno/mese.</span><span class="sxs-lookup"><span data-stu-id="d1547-129">The fault symptoms are now shown as registrations per year/month.</span></span>  
- <span data-ttu-id="d1547-130">Nella colonna **% probabilità**, se si sommano le percentuali di ogni mese, si ottiene 100%.</span><span class="sxs-lookup"><span data-stu-id="d1547-130">In the **Probability %** column, if you add all percentages for each month, they add up to 100%.</span></span> <span data-ttu-id="d1547-131">La probabilità è basata su tutte le registrazioni di **Sintomi** in questa analisi degli errori.</span><span class="sxs-lookup"><span data-stu-id="d1547-131">Probability is based on the **Symptom** registrations in this fault analysis.</span></span> <span data-ttu-id="d1547-132">Se il numero di righe in un cespite è elevato, ma una forte percentuale spicca in una riga, sarebbe un'indicazione di un sintomo di errore da esaminare più attentamente per trovare il modo di limitare il numero di registrazioni per quel sintomo di errore.</span><span class="sxs-lookup"><span data-stu-id="d1547-132">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault symptom to examine more closely to find a way to limit the number of registrations for that fault symptom.</span></span>

![Figura 2](media/07-controlling-and-reporting.png)

### <a name="group-by-multiple-symptoms-and-assets"></a><span data-ttu-id="d1547-134">Raggruppare per più sintomi e cespiti</span><span class="sxs-lookup"><span data-stu-id="d1547-134">Group by multiple symptoms and assets</span></span>

<span data-ttu-id="d1547-135">La combinazione di cespiti e un tipo di cespite sono utilizzati come base per i calcoli visualizzati nelle tre schermate seguenti, in cui il livello di dettagli aumenterà.</span><span class="sxs-lookup"><span data-stu-id="d1547-135">The combination of assets and an asset type is used as a basis for the calculations shown in the three screenshots below, which will increase in detail level.</span></span>  

<span data-ttu-id="d1547-136">In genere, i pulsanti nei gruppi di riquadri azioni **Raggruppa per data** **Raggruppa per cespite**, **Raggruppa per unità funzionale** nonché il pulsante **Errore** (ID errore), contengono periodi o relazioni cespiti.</span><span class="sxs-lookup"><span data-stu-id="d1547-136">Generally, the buttons in the **Group by date**, **Group by asset**, **Group by functional location** Action Pane groups, as well as the **Fault** button (Fault ID), contain periods or asset relations.</span></span> <span data-ttu-id="d1547-137">I pulsanti **Sintomo**, **Area**, **Tipo**, **Causa** e **Rimedio** sono categorizzazioni utilizzate nella gestione degli errori per analizzare le registrazioni di errore di cespite e individuare le aree con problemi.</span><span class="sxs-lookup"><span data-stu-id="d1547-137">The **Symptom**, **Area**, **Type**, **Cause**, and **Remedy** buttons are categorizations used in fault management to analyze asset fault registrations and pinpoint problem areas.</span></span>  

<span data-ttu-id="d1547-138">**Raggruppare per sintomo, cespite e tipo di cespite**</span><span class="sxs-lookup"><span data-stu-id="d1547-138">**Group by symptom, asset, and asset type**</span></span>

<span data-ttu-id="d1547-139">Nella schermata seguente, **Cespite** e **Tipo di cespite** sono stati aggiunti per offrire un maggiore livello di dettagli nelle registrazioni di errore.</span><span class="sxs-lookup"><span data-stu-id="d1547-139">In the screenshot below, **Asset** and **Asset type** were added to provide more detail regarding fault registrations.</span></span>

- <span data-ttu-id="d1547-140">I sintomi di errore sono ora suddivisi nelle combinazioni **Cespite** / **Tipo di cespite** / **Sintomo**.</span><span class="sxs-lookup"><span data-stu-id="d1547-140">The fault symptoms are now split up in **Asset** / **Asset type** / **Symptom** combinations.</span></span>  
- <span data-ttu-id="d1547-141">Nella colonna **% probabilità**, se si sommano le percentuali della combinazione di rispettivamente **Cespite** / **Tipo di cespite** / **Sintomo**, si ottiene 100%.</span><span class="sxs-lookup"><span data-stu-id="d1547-141">In the **Probability %** column, if you add all percentages for the combination of **Asset** / **Asset type** / **Symptom** respectively, they each add up to 100%.</span></span> <span data-ttu-id="d1547-142">La probabilità è basata su tutte le registrazioni di **Sintomi** in questa analisi degli errori.</span><span class="sxs-lookup"><span data-stu-id="d1547-142">Probability is based on **Symptom** registrations in this fault analysis.</span></span> <span data-ttu-id="d1547-143">Se il numero di righe in un cespite è elevato, ma una forte percentuale spicca in una riga, sarebbe un'indicazione di un sintomo di errore da esaminare più attentamente per trovare il modo di limitare il numero di registrazioni per quel sintomo di errore.</span><span class="sxs-lookup"><span data-stu-id="d1547-143">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault symptom to examine more closely to find a way to limit the number of registrations for that fault symptom.</span></span>

![Figura 3](media/08-controlling-and-reporting.png)

<span data-ttu-id="d1547-145">**Raggruppare per due sintomi, cespite e tipo di cespite**</span><span class="sxs-lookup"><span data-stu-id="d1547-145">**Group by two symptoms, asset, and asset type**</span></span>

<span data-ttu-id="d1547-146">Nella schermata seguente, **Area** è stato aggiunto a **Sintomo**, **Cespite** e **Tipo di cespite** per offrire un maggiore livello di dettagli nelle registrazioni di errore.</span><span class="sxs-lookup"><span data-stu-id="d1547-146">In the screenshot below, **Area** was added to **Symptom**, **Asset**, and **Asset type** to provide more detail regarding fault registrations.</span></span>

- <span data-ttu-id="d1547-147">Nella colonna **% probabilità**, se si sommano le percentuali della combinazione di **Cespite** / **Tipo di cespite** / **Sintomo**, si ottiene 100%.</span><span class="sxs-lookup"><span data-stu-id="d1547-147">In the **Probability %** column, if you add all percentages for the combination of **Asset** / **Asset type** / **Symptom** on an asset, they each add up to 100%.</span></span> <span data-ttu-id="d1547-148">La probabilità è basata sulla combinazione di **Sintomo** e **Area** in questa analisi degli errori.</span><span class="sxs-lookup"><span data-stu-id="d1547-148">Probability is based on the combination of **Symptom** and **Area** in this fault analysis.</span></span> <span data-ttu-id="d1547-149">Se il numero di righe in un cespite è elevato, ma una forte percentuale spicca in una riga, sarebbe un'indicazione di un'area di errore da esaminare più attentamente per trovare il modo di limitare il numero di registrazioni per quell'area di errore.</span><span class="sxs-lookup"><span data-stu-id="d1547-149">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault area to examine more closely to find a way to limit the number of registrations for that fault area.</span></span>  

![Figura 4](media/09-controlling-and-reporting.png)

<span data-ttu-id="d1547-151">**Raggruppare per tre sintomi, cespite e tipo di cespite**</span><span class="sxs-lookup"><span data-stu-id="d1547-151">**Group by three symptom, asset, and asset type**</span></span>

<span data-ttu-id="d1547-152">Nel schermata seguente, è stato aggiunto **Tipo** e viene visualizzato il calcolo più dettagliato in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="d1547-152">In the screenshot below, **Type** was added, and the most detailed calculation in this example is shown.</span></span>
 
- <span data-ttu-id="d1547-153">Nella colonna **% probabilità**, se si sommano le percentuali della combinazione di **Cespite** / **Tipo di cespite** / **Sintomo**, si ottiene 100%.</span><span class="sxs-lookup"><span data-stu-id="d1547-153">In the **Probability %** column, if you add all percentages for the combination of **Asset** / **Asset type** / **Symptom** on an asset, they each add up to 100%.</span></span> <span data-ttu-id="d1547-154">La probabilità è basata sulla combinazione di **Sintomo**, **Area** e **Tipo** in questa analisi degli errori.</span><span class="sxs-lookup"><span data-stu-id="d1547-154">Probability is based on the combination of **Symptom**, **Area**, and **Type** in this fault analysis.</span></span> <span data-ttu-id="d1547-155">Se il numero di righe in un cespite è elevato, ma una forte percentuale spicca in una riga, sarebbe un'indicazione di un tipo di errore da esaminare più attentamente per trovare il modo di limitare il numero di registrazioni per quel tipo di errore.</span><span class="sxs-lookup"><span data-stu-id="d1547-155">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault type to examine more closely to find a way to limit the number of registrations on that fault type.</span></span>

![Figura 5](media/10-controlling-and-reporting.png)


>[!NOTE]
><span data-ttu-id="d1547-157">Per una panoramica di tutte le registrazioni di errore create negli ordini di lavoro e nelle richieste di intervento di manutenzione, fare clic su **Gestione cespiti** > **Richieste di informazioni** > **Errore di cespite** > **Errori di cespite**.</span><span class="sxs-lookup"><span data-stu-id="d1547-157">For an overview of all fault registrations created on work orders and maintenance requests, click **Asset management** > **Inquiries** > **Asset fault** > **Asset faults**.</span></span> <span data-ttu-id="d1547-158">Nella pagina **Errori di cespite**, selezionare una registrazione ed espandere il riquadro **Informazioni correlate** per visualizzare informazioni relative alla richiesta di intervento di manutenzione o all'ordine di lavoro associato.</span><span class="sxs-lookup"><span data-stu-id="d1547-158">On the **Asset faults** page, select an asset fault registration and expand the **Related information** pane to see information regarding the related work order or maintenance request.</span></span>

