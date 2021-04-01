---
title: Implementare correzioni manuali nella previsione di base
description: Questo argomento illustra come apportare correzioni manuali a una previsione di base e visualizzare i dettagli della previsione.
author: roxanadiaconu
manager: tfehr
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanForecastViewer
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72704
ms.assetid: e7c5d44e-07bc-40b1-a4b3-8ba46483ef9e
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 90d19e9465abc71125931a7946febe2d633c3181
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5251963"
---
# <a name="make-manual-adjustments-to-the-baseline-forecast"></a><span data-ttu-id="dacff-103">Implementare correzioni manuali nella previsione di base</span><span class="sxs-lookup"><span data-stu-id="dacff-103">Make manual adjustments to the baseline forecast</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dacff-104">Questo argomento illustra come apportare correzioni manuali a una previsione di base e visualizzare i dettagli della previsione.</span><span class="sxs-lookup"><span data-stu-id="dacff-104">This topic explains how you can make manual adjustments to a baseline forecast and view details of the forecast.</span></span> 

<span data-ttu-id="dacff-105">Prima di apportare correzioni manuali, è importante comprendere alcuni concetti relativi alle varie pagine.</span><span class="sxs-lookup"><span data-stu-id="dacff-105">Before you make manual adjustments, it's important that you understand a few concepts on various pages.</span></span>

## <a name="grid-on-the-adjusted-demand-forecast-page"></a><span data-ttu-id="dacff-106">Griglia della pagina Previsione della domanda modificata</span><span class="sxs-lookup"><span data-stu-id="dacff-106">Grid on the Adjusted demand forecast page</span></span>
<span data-ttu-id="dacff-107">La pagina **Previsione della domanda modificata** include una griglia con la seguente struttura:</span><span class="sxs-lookup"><span data-stu-id="dacff-107">The **Adjusted demand forecast** page includes a grid that has the following structure:</span></span>

-   <span data-ttu-id="dacff-108">La prima colonna mostra gli articoli, le chiavi di allocazione articolo, le società, e così via, per cui la previsione è stata generata.</span><span class="sxs-lookup"><span data-stu-id="dacff-108">The first column shows the items, item allocation keys, companies, and so on, that the forecast has been generated for.</span></span> <span data-ttu-id="dacff-109">Il sottotitolo della pagina fornisce una descrizione delle dimensioni di previsione correnti visualizzate nella griglia.</span><span class="sxs-lookup"><span data-stu-id="dacff-109">The subtitle of the page provides a description of the current forecast dimensions that are shown in the grid.</span></span> <span data-ttu-id="dacff-110">Ad esempio, se il sottotitolo della pagina è **Società/sito/chiave di allocazione articolo** e una delle intestazioni della riga nella griglia è **USMF / 1 / D\_Alloc**, la riga mostra la previsione per la società USMF, il sito 1 e la chiave di allocazione articolo **D\_Alloc**.</span><span class="sxs-lookup"><span data-stu-id="dacff-110">For example, if the subtitle of the page is **Company / Site / Item allocation key**, and one of the row headers in the grid is **USMF / 1 / D\_Alloc**, that row shows the forecast for the USMF company, site 1, and the **D\_Alloc** item allocation key.</span></span>
-   <span data-ttu-id="dacff-111">Le colonne successive rappresentano gli intervalli di previsione per cui la previsione è stata generata.</span><span class="sxs-lookup"><span data-stu-id="dacff-111">Subsequent columns represent the forecast buckets that the forecast has been generated for.</span></span> <span data-ttu-id="dacff-112">Ogni intestazione di colonna corrisponde alla data dell'intervallo di previsione che mostra la colonna.</span><span class="sxs-lookup"><span data-stu-id="dacff-112">Each column header is the first date of the forecast bucket that the column shows.</span></span>
-   <span data-ttu-id="dacff-113">I valori delle celle rappresentano la previsione per un articolo, chiave di allocazione articolo, e altri valori specifici di tale intervallo di previsione.</span><span class="sxs-lookup"><span data-stu-id="dacff-113">The values in the cells represent the forecast for one item, item allocation key, and so on, for that specific forecast bucket.</span></span>

## <a name="forecast-aggregation-and-de-aggregation"></a><span data-ttu-id="dacff-114">Aggregazione e annullamento dell'aggregazione di previsione</span><span class="sxs-lookup"><span data-stu-id="dacff-114">Forecast aggregation and de-aggregation</span></span>
<span data-ttu-id="dacff-115">Il sottotitolo della pagina mostra il livello di aggregazione della previsione.</span><span class="sxs-lookup"><span data-stu-id="dacff-115">The subtitle of the page shows the level of forecast aggregation.</span></span> 

<span data-ttu-id="dacff-116">Ad esempio, se il sottotitolo della pagina è **Società/sito/chiave di allocazione/numero articolo/colore/dimensioni/configurazione/stile**, non esiste alcuna aggregazione di previsione e la previsione viene visualizzata a livello di articolo e delle relative dimensioni.</span><span class="sxs-lookup"><span data-stu-id="dacff-116">For example, if the subtitle of the page is **Company / Site / Allocation key / Item number / Color / Size / Configuration / Style**, there is no forecast aggregation, and the forecast is shown at the level of the item and its dimensions.</span></span> <span data-ttu-id="dacff-117">Per modificare l'aggregazione, utilizzare la pagina **Modifica dimensioni previsione** che è possibile aprire dal menu dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="dacff-117">To change the aggregation, use the **Change forecast dimensions** page, which you can open from the application menu.</span></span> 

<span data-ttu-id="dacff-118">Per modificare la previsione, fare clic su qualsiasi cella disponibile e digitare il valore corretto della previsione.</span><span class="sxs-lookup"><span data-stu-id="dacff-118">To modify the forecast, click in any of the cells that are available, and type the adjusted forecast value.</span></span> <span data-ttu-id="dacff-119">La cella modificata viene immediatamente evidenziata in grassetto per indicare che la previsione mostrata non corrisponde alla previsione creata dal servizio di previsione della domanda, ma al valore corretto manualmente.</span><span class="sxs-lookup"><span data-stu-id="dacff-119">The edited cell immediately becomes bold to indicate that the forecast that it shows isn't the forecast that the demand forecasting service created, but has been manually adjusted.</span></span> 

<span data-ttu-id="dacff-120">Se si modifica l'aggregazione affinché la pagina visualizzi ulteriori dati aggregati, è possibile utilizzare la pagina **Righe di previsione della domanda** per visualizzare le singole righe di previsione che costituiscono la previsione aggregata.</span><span class="sxs-lookup"><span data-stu-id="dacff-120">If you change the aggregation to make the page show more aggregated data, you can use the **Demand forecast lines** page to see the individual forecast lines that make up the aggregated forecast.</span></span> 

<span data-ttu-id="dacff-121">Ad esempio, è stata generata la previsione a livello di articolo, ma si sa che la domanda per l'articolo aumenterà in tutti i siti a causa di una promozione o di un altro evento simile.</span><span class="sxs-lookup"><span data-stu-id="dacff-121">For example, you've generated the forecast at the item level, but you know that the demand for this item will increase across all sites because of a promotion or another similar event.</span></span> <span data-ttu-id="dacff-122">In questo caso, è possibile impostare l'aggregazione su **Società / Chiave di allocazione articolo / Articolo** nella pagina **Modifica dimensioni previsione**.</span><span class="sxs-lookup"><span data-stu-id="dacff-122">In this case, you can set the aggregation to **Company / Item allocation key / Item** on the **Change forecast dimensions** page.</span></span> <span data-ttu-id="dacff-123">È possibile correggere la previsione globale per l'articolo in tutti i siti nella griglia **Previsione della domanda modificata**.</span><span class="sxs-lookup"><span data-stu-id="dacff-123">You can adjust the global forecast for the item across all sites in the **Adjusted demand forecast** grid.</span></span> <span data-ttu-id="dacff-124">Per visualizzare l'effetto della modifica in tutti i siti, aprire la pagina **Righe di previsione della domanda**.</span><span class="sxs-lookup"><span data-stu-id="dacff-124">To see the effect of your change across all sites, open the **Demand forecast lines** page.</span></span> <span data-ttu-id="dacff-125">In questa pagina, sarà possibile visualizzare una riga per l'articolo per ogni sito, la quantità di previsione corretta e la quantità di previsione originale.</span><span class="sxs-lookup"><span data-stu-id="dacff-125">On this page, you will see one line for the item for each site, the adjusted forecast quantity, and the original forecast quantity.</span></span> 

<span data-ttu-id="dacff-126">Quando la correzione della quantità programmata viene effettuata a livello aggregato, il sistema utilizza un metodo di allocazione pesato per distribuire la modifica tra le righe che creano l'aggregazione.</span><span class="sxs-lookup"><span data-stu-id="dacff-126">When the adjustment of the forecasted quantity is made at an aggregated level, the system uses weighted allocation to distribute the change among the lines that create the aggregation.</span></span> 

<span data-ttu-id="dacff-127">È inoltre possibile apportare correzioni manuali nella pagina **Righe di previsione della domanda** modificando il valore della **Quantità totale** o le celle della **Quantità** nella griglia di annullamento della aggregazione.</span><span class="sxs-lookup"><span data-stu-id="dacff-127">You can also make manual adjustments on the **Demand forecast lines** page, by modifying either the **Total quantity** value or the **Quantity** cells in the de-aggregation grid.</span></span>

## <a name="viewing-details-of-the-forecast"></a><span data-ttu-id="dacff-128">Visualizzazione dei dettagli della previsione</span><span class="sxs-lookup"><span data-stu-id="dacff-128">Viewing details of the forecast</span></span>
<span data-ttu-id="dacff-129">È possibile aprire la pagina **Dettagli di previsione della domanda** per visualizzare ulteriori informazioni sulla previsione.</span><span class="sxs-lookup"><span data-stu-id="dacff-129">You can open the **Demand forecast details** page to view more information about the forecast.</span></span> 

<span data-ttu-id="dacff-130">La pagina **Dettagli di previsione della domanda** visualizza le informazioni seguenti in formati grafici e tabulari:</span><span class="sxs-lookup"><span data-stu-id="dacff-130">The **Demand forecast details** page shows the following information in graphical and tabular formats:</span></span>

-   <span data-ttu-id="dacff-131">La domanda storica su cui si basano le previsioni.</span><span class="sxs-lookup"><span data-stu-id="dacff-131">The historical demand that the forecast predictions are based on.</span></span>
-   <span data-ttu-id="dacff-132">La previsione corrente utilizzata dalla pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="dacff-132">The current forecast that is used by Master planning.</span></span>
-   <span data-ttu-id="dacff-133">I nuovi valori di previsione della domanda e gli importi manualmente corretti.</span><span class="sxs-lookup"><span data-stu-id="dacff-133">The new demand forecast values and the amounts they have been manually adjusted by.</span></span>
-   <span data-ttu-id="dacff-134">L'intervallo di fiducia per i valori futuri.</span><span class="sxs-lookup"><span data-stu-id="dacff-134">The confidence interval for the forecasted values.</span></span>
-   <span data-ttu-id="dacff-135">Il modello previsionale utilizzato per generare la previsione.</span><span class="sxs-lookup"><span data-stu-id="dacff-135">The forecast model that was used to generate the forecast.</span></span> <span data-ttu-id="dacff-136">Se si visualizzano i dati aggregati, è possibile ottenere l'elenco di tutti i metodi utilizzati per tutte le serie cronologiche aggregate.</span><span class="sxs-lookup"><span data-stu-id="dacff-136">If you're viewing aggregated data, you will see the list of all the methods that were used for all the aggregated time series.</span></span>
-   <span data-ttu-id="dacff-137">La precisione del modello interno (Errore medio assoluto percentuale).</span><span class="sxs-lookup"><span data-stu-id="dacff-137">The internal model accuracy (MAPE).</span></span> <span data-ttu-id="dacff-138">Per ulteriori informazioni sulla precisione di previsione, vedere [Monitorare la precisione della previsione](monitor-forecast-accuracy.md).</span><span class="sxs-lookup"><span data-stu-id="dacff-138">For more information about forecast accuracy, see [Monitor forecast accuracy](monitor-forecast-accuracy.md).</span></span>

<span data-ttu-id="dacff-139">**Note:**</span><span class="sxs-lookup"><span data-stu-id="dacff-139">**Notes:**</span></span>

-   <span data-ttu-id="dacff-140">Se si abilita **Selezione del modello di previsione nei dettagli previsione della domanda** da Gestione funzionalità, sarà possibile selezionare i modelli di previsione da includere, per la previsione storica, nella pagina **Dettagli previsione della domanda**.</span><span class="sxs-lookup"><span data-stu-id="dacff-140">If you enable **Forecast model selection on Demand forecast details** from Feature management, you will be able to select the forecast models to be include, for the historical forecast, on the **Demand forecast details** page.</span></span>
-   <span data-ttu-id="dacff-141">L'intervallo di fiducia visualizzato nella sezione **Previsione** della pagina rappresenta la differenza tra il limite superiore dell'intervallo di fiducia e il limite minimo dell'intervallo di fiducia.</span><span class="sxs-lookup"><span data-stu-id="dacff-141">The confidence interval that appears in the **Forecast** section of the page represents the difference between the confidence interval upper limit and the confidence interval lower limit.</span></span> <span data-ttu-id="dacff-142">Per visualizzare i valori dei limiti superiori e inferiori, passare il mouse sul grafico nella sezione **Domanda e previsioni storiche in formato grafico**.</span><span class="sxs-lookup"><span data-stu-id="dacff-142">To see the values for the upper and lower limits, hover over the chart in the **Historical demand and forecast graphically** section.</span></span>
-   <span data-ttu-id="dacff-143">Se si utilizza Microsoft Azure Machine Learning di previsione della domanda, è possibile specificare la percentuale del livello di fiducia che la previsione generata deve avere.</span><span class="sxs-lookup"><span data-stu-id="dacff-143">If you use the Demand forecasting Microsoft Azure Machine Learning, you can specify the confidence level percentage that the forecast that is generated should have.</span></span> <span data-ttu-id="dacff-144">Un intervallo di fiducia è costituito da un intervallo di valori che fungono da stime affidabili per la previsione della domanda.</span><span class="sxs-lookup"><span data-stu-id="dacff-144">A confidence interval consists of a range of values that act as good estimates for the demand forecast.</span></span> <span data-ttu-id="dacff-145">Un livello di fiducia del 95% indica ad esempio che è presente una possibilità del 5% che il risultato di previsione della domanda previsto non sia compreso nell'intervallo stabilito.</span><span class="sxs-lookup"><span data-stu-id="dacff-145">A 95-percent confidence level percentage indicates that there is a 5-percent risk that the demand forecast falls outside the confidence interval range.</span></span>

<span data-ttu-id="dacff-146">È inoltre possibile apportare correzioni manuali alla previsione nella pagina **Dettagli previsione della domanda** modificando i valori della riga **Previsione** nella sezione **Previsione**.</span><span class="sxs-lookup"><span data-stu-id="dacff-146">You can also make manual adjustments to the forecast on the **Demand forecast details** page, by modifying the values in the **Forecast** row in the **Forecast** section.</span></span>

<a name="additional-resources"></a><span data-ttu-id="dacff-147">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="dacff-147">Additional resources</span></span>
--------

[<span data-ttu-id="dacff-148">Monitorare la precisione della previsione</span><span class="sxs-lookup"><span data-stu-id="dacff-148">Monitor forecast accuracy</span></span>](monitor-forecast-accuracy.md)

[<span data-ttu-id="dacff-149">Generare una previsione di base statistica</span><span class="sxs-lookup"><span data-stu-id="dacff-149">Generate a statistical baseline forecast</span></span>](generate-statistical-baseline-forecast.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]