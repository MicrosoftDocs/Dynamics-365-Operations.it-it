---
title: Creare una previsione di base
description: Un responsabile di pianificazione della produzione può creare una previsione di base utilizzando i modelli previsionali delle serie temporali o copiando la domanda storica.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup, ReqIntercompanyPlanningGroupAllocKeys, ReqDemPlanForecastParameters, ReqDemPlanCreateForecastDialog, SysQueryForm, ReqDemPlanForecastViewer
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 47e26a48cdde3a6996f4c0a4ca85222c402f44e2
ms.sourcegitcommit: 436731d8b3889bebfe6f17922b0a31b1994f6796
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/26/2020
ms.locfileid: "4431588"
---
# <a name="create-a-baseline-forecast"></a><span data-ttu-id="62925-103">Creare una previsione di base</span><span class="sxs-lookup"><span data-stu-id="62925-103">Create a baseline forecast</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="62925-104">Un responsabile di pianificazione della produzione può creare una previsione di base utilizzando i modelli previsionali delle serie temporali o copiando la domanda storica.</span><span class="sxs-lookup"><span data-stu-id="62925-104">A production planner can create a baseline forecast either by using time series forecast models or by copying the historical demand.</span></span> <span data-ttu-id="62925-105">Questa procedura illustra come copiare la domanda storica per creare una previsione di base per tutti i prodotti utilizzando una chiave di allocazione articolo.</span><span class="sxs-lookup"><span data-stu-id="62925-105">This procedure shows how to copy the historical demand to create a baseline forecast for all products using one item allocation key.</span></span> 


## <a name="set-up-an-item-allocation-key"></a><span data-ttu-id="62925-106">Impostare una chiave di allocazione articolo</span><span class="sxs-lookup"><span data-stu-id="62925-106">Set up an item allocation key</span></span>
1. <span data-ttu-id="62925-107">Andare a Pianificazione generale > Impostazioni > Gruppi di pianificazione interaziendale.</span><span class="sxs-lookup"><span data-stu-id="62925-107">Go to Master planning > Setup > Intercompany planning groups.</span></span>
2. <span data-ttu-id="62925-108">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="62925-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="62925-109">Ad esempio, applicare un filtro nel campo Nome con un valore "10".</span><span class="sxs-lookup"><span data-stu-id="62925-109">For example, filter on the Name field with a value of '10'.</span></span>
    * <span data-ttu-id="62925-110">La previsione della domanda viene eseguita tra le persone giuridiche.</span><span class="sxs-lookup"><span data-stu-id="62925-110">Demand forecasting runs across legal entities.</span></span> <span data-ttu-id="62925-111">Per questo motivo è necessario impostare tutte le società per cui si desidera generare previsioni in un gruppo di pianificazione interaziendale.</span><span class="sxs-lookup"><span data-stu-id="62925-111">That's why you need to set up all the companies for which you want to generate forecasts in one intercompany planning group.</span></span>  
3. <span data-ttu-id="62925-112">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="62925-112">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="62925-113">Fare clic su Chiavi di allocazione articoli.</span><span class="sxs-lookup"><span data-stu-id="62925-113">Click Item allocation keys.</span></span>
    * <span data-ttu-id="62925-114">Selezionare tutte le chiavi di allocazione articolo per il quale si desidera creare previsioni.</span><span class="sxs-lookup"><span data-stu-id="62925-114">Select all the item allocation keys for which you want to create forecasts.</span></span>  
5. <span data-ttu-id="62925-115">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="62925-115">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="62925-116">Selezionare la chiave di allocazione articolo D_Aloc.</span><span class="sxs-lookup"><span data-stu-id="62925-116">Select D_Aloc item allocation key.</span></span>  
6. <span data-ttu-id="62925-117">Fare clic su >.</span><span class="sxs-lookup"><span data-stu-id="62925-117">Click >.</span></span>
7. <span data-ttu-id="62925-118">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="62925-118">Close the page.</span></span>
8. <span data-ttu-id="62925-119">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="62925-119">Close the page.</span></span>

## <a name="set-up-the-demand-forecasting-parameters"></a><span data-ttu-id="62925-120">Impostare i parametri della previsione della domanda</span><span class="sxs-lookup"><span data-stu-id="62925-120">Set up the demand forecasting parameters</span></span>
1. <span data-ttu-id="62925-121">Andare a Pianificazione generale > Impostazioni > Previsione della domanda > Parametri di previsione della domanda.</span><span class="sxs-lookup"><span data-stu-id="62925-121">Go to Master planning > Setup > Demand forecasting > Demand forecasting parameters.</span></span>
2. <span data-ttu-id="62925-122">Espandere la sezione Parametri dell'algoritmo di previsione.</span><span class="sxs-lookup"><span data-stu-id="62925-122">Expand the Forecast algorithm parameters section.</span></span>
3. <span data-ttu-id="62925-123">Nel campo Strategia di generazione previsione selezionare "Copia domanda storica".</span><span class="sxs-lookup"><span data-stu-id="62925-123">In the Forecast generation strategy field, select 'Copy over historical demand'.</span></span>
4. <span data-ttu-id="62925-124">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="62925-124">Click Save.</span></span>

## <a name="create-a-baseline-forecast"></a><span data-ttu-id="62925-125">Creare una previsione di base</span><span class="sxs-lookup"><span data-stu-id="62925-125">Create a baseline forecast</span></span>
1. <span data-ttu-id="62925-126">Andare a Pianificazione generale > Previsioni > Previsione della domanda > Genera previsione di base statistica.</span><span class="sxs-lookup"><span data-stu-id="62925-126">Go to Master planning > Forecasting > Demand forecasting > Generate statistical baseline forecast.</span></span>
2. <span data-ttu-id="62925-127">Immettere una data nel campo Dal.</span><span class="sxs-lookup"><span data-stu-id="62925-127">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="62925-128">Se sono presenti ordini cliente a partire dal 1° gennaio 2015, inserire questa data.</span><span class="sxs-lookup"><span data-stu-id="62925-128">If you have sales orders starting from January 1, 2015, enter this date.</span></span> <span data-ttu-id="62925-129">In caso negativo, immettere la prima data degli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="62925-129">If you don't, enter the earliest date of your sales orders.</span></span>  
3. <span data-ttu-id="62925-130">Nel campo Data finale immettere una data.</span><span class="sxs-lookup"><span data-stu-id="62925-130">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="62925-131">Immettere l'ultima data degli ordini cliente, ad esempio "31-03-2015".</span><span class="sxs-lookup"><span data-stu-id="62925-131">Enter the last date of your sales orders, for example '2015-03-31'.</span></span>  
4. <span data-ttu-id="62925-132">Immettere una data nel campo Dal.</span><span class="sxs-lookup"><span data-stu-id="62925-132">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="62925-133">Immettere "01-04-2015".</span><span class="sxs-lookup"><span data-stu-id="62925-133">Enter '2015-04-01'.</span></span> <span data-ttu-id="62925-134">Questa data verrà calcolata automaticamente come data di inizio dell'intervallo di tempo di previsione.</span><span class="sxs-lookup"><span data-stu-id="62925-134">This date will be automatically calculated as the start date of the next forecasting bucket.</span></span>  
5. <span data-ttu-id="62925-135">Espandere la sezione Record da includere.</span><span class="sxs-lookup"><span data-stu-id="62925-135">Expand the Records to include section.</span></span>
6. <span data-ttu-id="62925-136">Fare clic su Filtro.</span><span class="sxs-lookup"><span data-stu-id="62925-136">Click Filter.</span></span>
7. <span data-ttu-id="62925-137">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="62925-137">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="62925-138">Contrassegnare la riga in cui Campo = Gruppo di pianificazione interaziendale.</span><span class="sxs-lookup"><span data-stu-id="62925-138">Mark the row where Field = Intercompany planning group.</span></span>  
8. <span data-ttu-id="62925-139">Digitare un valore nel campo Criteri.</span><span class="sxs-lookup"><span data-stu-id="62925-139">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="62925-140">Immettere il gruppo di pianificazione interaziendale, ad esempio 10, utilizzato nella prima attività.</span><span class="sxs-lookup"><span data-stu-id="62925-140">Type the intercompany planning group, for example, 10, that you used in the first task.</span></span>  
9. <span data-ttu-id="62925-141">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="62925-141">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="62925-142">Selezionare la riga in cui Campo = Chiave di allocazione articolo.</span><span class="sxs-lookup"><span data-stu-id="62925-142">Select the row where Field = Item allocation key.</span></span>  
10. <span data-ttu-id="62925-143">Digitare un valore nel campo Criteri.</span><span class="sxs-lookup"><span data-stu-id="62925-143">In the Criteria field, type a value.</span></span>
11. <span data-ttu-id="62925-144">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="62925-144">Click OK.</span></span>
12. <span data-ttu-id="62925-145">Espandere la sezione Parametri avanzati.</span><span class="sxs-lookup"><span data-stu-id="62925-145">Expand the Advanced parameters section.</span></span>
13. <span data-ttu-id="62925-146">Nel campo Intervallo di tempo previsioni selezionare "Mese".</span><span class="sxs-lookup"><span data-stu-id="62925-146">In the Forecast bucket field, select 'Month'.</span></span>
14. <span data-ttu-id="62925-147">Nel campo Orizzonte previsione immettere "3".</span><span class="sxs-lookup"><span data-stu-id="62925-147">In the Forecast horizon field, enter '3'.</span></span>
15. <span data-ttu-id="62925-148">Nel campo Intervallo temporale blocco immettere "1".</span><span class="sxs-lookup"><span data-stu-id="62925-148">In the Freeze time fence field, enter '1'.</span></span>
16. <span data-ttu-id="62925-149">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="62925-149">Click OK.</span></span>

## <a name="visualize-the-demand-forecast"></a><span data-ttu-id="62925-150">Visualizzare la previsione della domanda</span><span class="sxs-lookup"><span data-stu-id="62925-150">Visualize the demand forecast</span></span>
1. <span data-ttu-id="62925-151">Andare a Pianificazione generale > Previsioni > Previsione della domanda > Previsione della domanda modificata.</span><span class="sxs-lookup"><span data-stu-id="62925-151">Go to Master planning > Forecasting > Demand forecasting > Adjusted demand forecast.</span></span>
2. <span data-ttu-id="62925-152">Nella tabella della visualizzazione aggregata, selezionare la cella nella riga 1, colonna 2.</span><span class="sxs-lookup"><span data-stu-id="62925-152">In the aggregated view table, select the cell in row 1, column 2.</span></span> <span data-ttu-id="62925-153">È il secondo mese per il quale è stata creata la previsione.</span><span class="sxs-lookup"><span data-stu-id="62925-153">This is the second month for which you have created forecast.</span></span>
3. <span data-ttu-id="62925-154">Impostare QtyCell su "400".</span><span class="sxs-lookup"><span data-stu-id="62925-154">Set QtyCell to '400'.</span></span>
    * <span data-ttu-id="62925-155">Nella cella immettere un numero diverso da quello previsto, ad esempio 400.</span><span class="sxs-lookup"><span data-stu-id="62925-155">In the cell, enter a different number than the one that was forecasted, for example, 400.</span></span>  
4. <span data-ttu-id="62925-156">È stata effettuata una rettifica manuale alla previsione.</span><span class="sxs-lookup"><span data-stu-id="62925-156">You have made a manual adjustment to the forecast.</span></span> <span data-ttu-id="62925-157">Si noti l'indicazione grafica al passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="62925-157">Notice the graphical indication in the next step.</span></span>
5. <span data-ttu-id="62925-158">Fare clic su Dettagli riga previsione.</span><span class="sxs-lookup"><span data-stu-id="62925-158">Click Forecast line details.</span></span>
    * <span data-ttu-id="62925-159">In questa pagina è possibile visualizzare i valori di precisione, la domanda storica e la previsione.</span><span class="sxs-lookup"><span data-stu-id="62925-159">In this page, you can see the accuracy values, historical demand, and forecast.</span></span> <span data-ttu-id="62925-160">È inoltre possibile modificare la previsione.</span><span class="sxs-lookup"><span data-stu-id="62925-160">You can make changes to the forecast as well.</span></span>  

