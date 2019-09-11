---
title: Analisi degli errori dei cespiti
description: In questo argomento viene descritta l'analisi degli errori di cespite in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7c9330cc7b3a8839d94c8945418548033254786b
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918443"
---
# <a name="asset-fault-analysis"></a><span data-ttu-id="27444-103">Analisi degli errori dei cespiti</span><span class="sxs-lookup"><span data-stu-id="27444-103">Asset fault analysis</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="27444-104">In Gestione cespiti, è possibile analizzare le registrazioni di errore di cespite per ottenere una panoramica del numero totale di errori registrati durante un periodo specifico.</span><span class="sxs-lookup"><span data-stu-id="27444-104">In Asset Management, you can analyze asset fault registrations to get an overview of the total number of faults registered during a specific period.</span></span> <span data-ttu-id="27444-105">Le registrazioni di errore possono essere analizzate da varie prospettive, ad esempio in relazione cespiti, tipi di cespite, unità funzionali, sintomi di errore o tipi di errore.</span><span class="sxs-lookup"><span data-stu-id="27444-105">Fault registrations can be analyzed from different perspectives, for example with focus on assets, asset types, functional locations, fault symptoms, or fault types.</span></span>

1. <span data-ttu-id="27444-106">Fare clic su **Gestione cespiti** > **Richieste di informazioni** > **Errore di cespite** > **Analisi degli errori dei cespiti**.</span><span class="sxs-lookup"><span data-stu-id="27444-106">Click **Asset management** > **Inquiries** > **Asset fault** > **Asset fault analysis**.</span></span>

2. <span data-ttu-id="27444-107">Nella finestra di dialogo **Calcolo analisi errori dei cespiti**, è possibile utilizzare il campo **Livello** per indicare il livello di dettagli delle righe degli errori di cespite in relazione alle unità funzionali.</span><span class="sxs-lookup"><span data-stu-id="27444-107">In the **Asset fault analysis calculation** dialog, you can use the **Level** field to indicate how detailed you want the asset fault lines to be regarding functional locations.</span></span> <span data-ttu-id="27444-108">Ad esempio, se si inserisce "1" nel campo e si ha una struttura di unità funzionali multilivello, tutte le righe degli errori di cespite per un'unità funzionale verranno visualizzate nel livello principale, quindi le ore in una riga possono essere aggiunte dalle unità funzionali situate a un livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="27444-108">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all asset fault lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> <span data-ttu-id="27444-109">Se si inserisce "0" nel campo **Livello**, verrà visualizzato un risultato dettagliato che mostra tutte le righe degli errori di cespite in tutti i livelli di unità funzionali a cui sono correlate.</span><span class="sxs-lookup"><span data-stu-id="27444-109">If you insert the number "0" in the **Level** field, you will see a detailed result showing all asset fault lines on all the functional location level to which they are related.</span></span>

3. <span data-ttu-id="27444-110">Se si desidera limitare la ricerca, è possibile selezionare specifici cespiti, date di errore, cause di errore e rimedi agli errori nella Scheda dettaglio **Record da includere**.</span><span class="sxs-lookup"><span data-stu-id="27444-110">If you want to limit the search, you can select specific assets, fault dates, fault causes, and fault remedies on the **Records to include** FastTab.</span></span>

4. <span data-ttu-id="27444-111">Fare clic su **OK** per avviare il calcolo.</span><span class="sxs-lookup"><span data-stu-id="27444-111">Click **OK** to start the calculation.</span></span>

5. <span data-ttu-id="27444-112">Nella scheda **Analisi degli errori dei cespiti**, fare clic su uno o più pulsanti nei gruppi di riquadri azioni **Raggruppa per** per visualizzare il livello di dettagli desiderato.</span><span class="sxs-lookup"><span data-stu-id="27444-112">On the **Asset fault analysis** tab, click one or more buttons in the **Group by...** action pane groups to display the detail level you want to see.</span></span> <span data-ttu-id="27444-113">I pulsanti attivati sono evidenziati.</span><span class="sxs-lookup"><span data-stu-id="27444-113">Activated buttons are highlighted.</span></span> <span data-ttu-id="27444-114">Fare clic sui pulsanti per attivarli o disattivarli.</span><span class="sxs-lookup"><span data-stu-id="27444-114">Activate or deactivate buttons by clicking on them.</span></span>

6. <span data-ttu-id="27444-115">Fare clic su **Aggiorna calcoli** per visualizzare le selezioni sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="27444-115">Click **Update calculations** to show your selections on the screen.</span></span> 

>[!NOTE]
><span data-ttu-id="27444-116">Ogni volta che si attivano o si disattivano i pulsanti nei gruppi di riquadri azioni **Raggruppa per**, ricordarsi di fare clic sul pulsante **Aggiorna calcoli** dopo aver modificato le selezioni.</span><span class="sxs-lookup"><span data-stu-id="27444-116">Every time you activate or deactivate buttons in the **Group by...** action pane groups, remember to click the **Update calculations** button after you changed the selections.</span></span> <span data-ttu-id="27444-117">Ciò è necessario in quanto una grande quantità di dati viene elaborata durante il ricalcolo della probabilità di errore.</span><span class="sxs-lookup"><span data-stu-id="27444-117">This is required because a large amount of data is processed as you are recalculating fault probability.</span></span>

<span data-ttu-id="27444-118">Esistono vari modi di analizzare le registrazioni di errore.</span><span class="sxs-lookup"><span data-stu-id="27444-118">There are many ways to analyze fault registrations.</span></span> <span data-ttu-id="27444-119">Di seguito sono illustrate cinque schermate di esempio su come differenti selezioni di dati forniscono informazioni differenti.</span><span class="sxs-lookup"><span data-stu-id="27444-119">Below you see examples in five screenshots of how different data selections provide different pieces of information.</span></span> <span data-ttu-id="27444-120">Sarà possibile osservare come differenti selezioni forniscono più informazioni e dettagli durante l'analisi delle registrazioni di errore di cespite.</span><span class="sxs-lookup"><span data-stu-id="27444-120">You will see how different selections provide more insight and detail when analyzing asset fault registrations.</span></span>

<span data-ttu-id="27444-121">Nel schermata seguente, solo il pulsante **Sintomo** è selezionato.</span><span class="sxs-lookup"><span data-stu-id="27444-121">In the screenshot below, only the **Symptom** button is selected.</span></span>

- <span data-ttu-id="27444-122">Le registrazioni di errore sono state effettuate per tre sintomi di errore: "Perdita d'aria", "Fusibile bruciato" e "attrezzatura inceppata".</span><span class="sxs-lookup"><span data-stu-id="27444-122">Fault registrations have been made on three fault symptoms: "Air leak", "Blown fuse", and "Equipment jammed".</span></span>  
- <span data-ttu-id="27444-123">Nella colonna **% probabilità**, la somma di tutte le percentuali equivale al 100%.</span><span class="sxs-lookup"><span data-stu-id="27444-123">In the **Probability %** column, all percentages add up to 100%.</span></span> <span data-ttu-id="27444-124">La probabilità è basata su tutte le registrazioni di **Sintomi** in questa analisi degli errori.</span><span class="sxs-lookup"><span data-stu-id="27444-124">Probability is based on all **Symptom** registrations in this fault analysis.</span></span>

![Figura 1](media/06-controlling-and-reporting.png)


<span data-ttu-id="27444-126">Nella schermata seguente, sono stati aggiunti **Anno** e **Mese** per mostrare come è possibile visualizzare le registrazioni di errore durante un periodo selezionato.</span><span class="sxs-lookup"><span data-stu-id="27444-126">In the screenshot below, **Year** and **Month** are added to show how you can view fault registrations during a selected period.</span></span>

- <span data-ttu-id="27444-127">I sintomi di errore sono ora visualizzati come registrazioni per anno/mese.</span><span class="sxs-lookup"><span data-stu-id="27444-127">The fault symptoms are now shown as registrations per year/month.</span></span>  
- <span data-ttu-id="27444-128">Nella colonna **% probabilità**, se si sommano le percentuali di ogni mese, si ottiene 100%.</span><span class="sxs-lookup"><span data-stu-id="27444-128">In the **Probability %** column, if you add all percentages for each month, they add up to 100%.</span></span> <span data-ttu-id="27444-129">La probabilità è basata su tutte le registrazioni di **Sintomi** in questa analisi degli errori.</span><span class="sxs-lookup"><span data-stu-id="27444-129">Probability is based on the **Symptom** registrations in this fault analysis.</span></span> <span data-ttu-id="27444-130">Se il numero di righe in un cespite è elevato, ma una forte percentuale spicca in una riga, sarebbe un'indicazione di un sintomo di errore da esaminare più attentamente per trovare il modo di limitare il numero di registrazioni per quel sintomo di errore.</span><span class="sxs-lookup"><span data-stu-id="27444-130">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault symptom to examine more closely to find a way to limit the number of registrations for that fault symptom.</span></span>

![Figura 2](media/07-controlling-and-reporting.png)


- <span data-ttu-id="27444-132">La combinazione di cespiti e un tipo di cespite sono utilizzati come base per i calcoli visualizzati nelle tre schermate seguenti, in cui il livello di dettagli aumenterà.</span><span class="sxs-lookup"><span data-stu-id="27444-132">The combination of assets and an asset type is used as a basis for the calculations shown in the three screenshots below, which will increase in detail level.</span></span>  
- <span data-ttu-id="27444-133">In genere, i pulsanti nei gruppi di riquadri azioni **Raggruppa per data** **Raggruppa per cespite**, **Raggruppa per unità funzionale** nonché il pulsante **Errore** (ID errore), contengono periodi o relazioni cespiti.</span><span class="sxs-lookup"><span data-stu-id="27444-133">Generally, the buttons in the **Group by date**, **Group by asset**, **Group by functional location** action pane groups, as well as the **Fault** button (Fault ID), contain periods or asset relations.</span></span> <span data-ttu-id="27444-134">I pulsanti **Sintomo**, **Area**, **Tipo**, **Causa** e **Rimedio** sono categorizzazioni utilizzate nella gestione degli errori per analizzare le registrazioni di errore di cespite e individuare le aree con problemi.</span><span class="sxs-lookup"><span data-stu-id="27444-134">The **Symptom**, **Area**, **Type**, **Cause**, and **Remedy** buttons are categorizations used in fault management to analyze asset fault registrations and pinpoint problem areas.</span></span>  

<span data-ttu-id="27444-135">Nella schermata seguente, **Cespite** e **Tipo di cespite** sono stati aggiunti per offrire un maggiore livello di dettagli nelle registrazioni di errore.</span><span class="sxs-lookup"><span data-stu-id="27444-135">In the screenshot below, **Asset** and **Asset type** were added to provide more detail regarding fault registrations.</span></span>

- <span data-ttu-id="27444-136">I sintomi di errore sono ora suddivisi nelle combinazioni **Cespite** / **Tipo di cespite** / **Sintomo**.</span><span class="sxs-lookup"><span data-stu-id="27444-136">The fault symptoms are now split up in **Asset** / **Asset type** / **Symptom** combinations.</span></span>  
- <span data-ttu-id="27444-137">Nella colonna **% probabilità**, se si sommano le percentuali della combinazione di rispettivamente **Cespite** / **Tipo di cespite** / **Sintomo**, si ottiene 100%.</span><span class="sxs-lookup"><span data-stu-id="27444-137">In the **Probability %** column, if you add all percentages for the combination of **Asset** / **Asset type** / **Symptom** respectively, they each add up to 100%.</span></span> <span data-ttu-id="27444-138">La probabilità è basata su tutte le registrazioni di **Sintomi** in questa analisi degli errori.</span><span class="sxs-lookup"><span data-stu-id="27444-138">Probability is based on **Symptom** registrations in this fault analysis.</span></span> <span data-ttu-id="27444-139">Se il numero di righe in un cespite è elevato, ma una forte percentuale spicca in una riga, sarebbe un'indicazione di un sintomo di errore da esaminare più attentamente per trovare il modo di limitare il numero di registrazioni per quel sintomo di errore.</span><span class="sxs-lookup"><span data-stu-id="27444-139">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault symptom to examine more closely to find a way to limit the number of registrations for that fault symptom.</span></span>

![Figura 3](media/08-controlling-and-reporting.png)


<span data-ttu-id="27444-141">Nella schermata seguente, **Area** è stato aggiunto a **Sintomo**, **Cespite** e **Tipo di cespite** per offrire un maggiore livello di dettagli nelle registrazioni di errore.</span><span class="sxs-lookup"><span data-stu-id="27444-141">In the screenshot below, **Area** was added to **Symptom**, **Asset**, and **Asset type** to provide more detail regarding fault registrations.</span></span>

- <span data-ttu-id="27444-142">Nella colonna **% probabilità**, se si sommano le percentuali della combinazione di **Cespite** / **Tipo di cespite** / **Sintomo**, si ottiene 100%.</span><span class="sxs-lookup"><span data-stu-id="27444-142">In the **Probability %** column, if you add all percentages for the combination of **Asset** / **Asset type** / **Symptom** on an asset, they each add up to 100%.</span></span> <span data-ttu-id="27444-143">La probabilità è basata sulla combinazione di **Sintomo** e **Area** in questa analisi degli errori.</span><span class="sxs-lookup"><span data-stu-id="27444-143">Probability is based on the combination of **Symptom** and **Area** in this fault analysis.</span></span> <span data-ttu-id="27444-144">Se il numero di righe in un cespite è elevato, ma una forte percentuale spicca in una riga, sarebbe un'indicazione di un'area di errore da esaminare più attentamente per trovare il modo di limitare il numero di registrazioni per quell'area di errore.</span><span class="sxs-lookup"><span data-stu-id="27444-144">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault area to examine more closely to find a way to limit the number of registrations for that fault area.</span></span>  

![Figura 4](media/09-controlling-and-reporting.png)


<span data-ttu-id="27444-146">Nel schermata seguente, è stato aggiunto **Tipo** e viene visualizzato il calcolo più dettagliato in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="27444-146">In the screenshot below, **Type** was added, and the most detailed calculation in this example is shown.</span></span>
 
- <span data-ttu-id="27444-147">Nella colonna **% probabilità**, se si sommano le percentuali della combinazione di **Cespite** / **Tipo di cespite** / **Sintomo**, si ottiene 100%.</span><span class="sxs-lookup"><span data-stu-id="27444-147">In the **Probability %** column, if you add all percentages for the combination of **Asset** / **Asset type** / **Symptom** on an asset, they each add up to 100%.</span></span> <span data-ttu-id="27444-148">La probabilità è basata sulla combinazione di **Sintomo**, **Area** e **Tipo** in questa analisi degli errori.</span><span class="sxs-lookup"><span data-stu-id="27444-148">Probability is based on the combination of **Symptom**, **Area**, and **Type** in this fault analysis.</span></span> <span data-ttu-id="27444-149">Se il numero di righe in un cespite è elevato, ma una forte percentuale spicca in una riga, sarebbe un'indicazione di un tipo di errore da esaminare più attentamente per trovare il modo di limitare il numero di registrazioni per quel tipo di errore.</span><span class="sxs-lookup"><span data-stu-id="27444-149">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault type to examine more closely to find a way to limit the number of registrations on that fault type.</span></span>

![Figura 5](media/10-controlling-and-reporting.png)


>[!NOTE]
><span data-ttu-id="27444-151">Per una panoramica di tutte le registrazioni di errore create negli ordini di lavoro e nelle richieste di intervento di manutenzione, fare clic su **Gestione cespiti** > **Richieste di informazioni** > **Errore di cespite** > **Errori di cespite**.</span><span class="sxs-lookup"><span data-stu-id="27444-151">For an overview of all fault registrations created on work orders and maintenance requests, click **Asset management** > **Inquiries** > **Asset fault** > **Asset faults**.</span></span> <span data-ttu-id="27444-152">Nella pagina **Errori di cespite**, selezionare una registrazione ed espandere il riquadro **Informazioni correlate** per visualizzare informazioni relative alla richiesta di intervento di manutenzione o all'ordine di lavoro associato.</span><span class="sxs-lookup"><span data-stu-id="27444-152">On the **Asset faults** page, select an asset fault registration and expand the **Related information** pane to see information regarding the related work order or maintenance request.</span></span>

