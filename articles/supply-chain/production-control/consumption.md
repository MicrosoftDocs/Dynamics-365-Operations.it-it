---
title: Calcolare il consumo di materiali
description: Questo articolo fornisce informazioni sulle varie opzioni correlate al calcolo del consumo materiali.
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMDesignerEditBOM, BOMTable, ProdBOM
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 53401
ms.assetid: 9cff88e4-0425-4707-9178-3c2cb10df7c2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: f674a1f0051ee4b228b8a92f717ef5348a452bed
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="calculate-material-consumption"></a><span data-ttu-id="bb178-103">Calcolare il consumo di materiali</span><span class="sxs-lookup"><span data-stu-id="bb178-103">Calculate material consumption</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="bb178-104">Questo articolo fornisce informazioni sulle varie opzioni correlate al calcolo del consumo materiali.</span><span class="sxs-lookup"><span data-stu-id="bb178-104">This article provides information about various options that are related to the calculation of material consumption.</span></span> 

<span data-ttu-id="bb178-105">Le seguenti opzioni correlate al calcolo del consumo di materiali sono disponibili nelle schede **Impostazioni** e **Consumo fase** della scheda dettaglio **Dettagli riga** nella pagina **Distinta base**.</span><span class="sxs-lookup"><span data-stu-id="bb178-105">The following options that are related to the calculation of material consumption are available on the **Setup** and **Step consumption** tabs on the **Line details** FastTab of the **Bill of materials** page.</span></span>

## <a name="variable-and-constant-consumption"></a><span data-ttu-id="bb178-106">Consumo variabile e costante</span><span class="sxs-lookup"><span data-stu-id="bb178-106">Variable and constant consumption</span></span>
<span data-ttu-id="bb178-107">Nel campo **Il consumo è** è possibile scegliere se il consumo deve essere calcolato come una quantità costante o variabile.</span><span class="sxs-lookup"><span data-stu-id="bb178-107">In the **Consumption is** field, you can select whether consumption should be calculated as a constant quantity or a variable quantity.</span></span> <span data-ttu-id="bb178-108">Selezionare **Costante** se per la produzione è necessario utilizzare una quantità o un volume fisso, indipendentemente dalla quantità prodotta.</span><span class="sxs-lookup"><span data-stu-id="bb178-108">Select **Constant** if a fixed quantity or volume is required for the production, regardless of the quantity that is produced.</span></span> <span data-ttu-id="bb178-109">Selezionare **la variabile**, ovvero l'impostazione predefinita, se la quantità di materiale richiesta i prodotti finiti è proporzionale al numero di prodotti finiti che vengono prodotti.</span><span class="sxs-lookup"><span data-stu-id="bb178-109">Select **Variable**, which is the default setting, if the required amount of material in the finished goods is proportional to the number of finished goods that are produced.</span></span>

## <a name="calculating-consumption-from-a-formula"></a><span data-ttu-id="bb178-110">Calcolo del consumo tramite una formula</span><span class="sxs-lookup"><span data-stu-id="bb178-110">Calculating consumption from a formula</span></span>
<span data-ttu-id="bb178-111">Nel campo **Formula** è possibile impostare diverse formule per il calcolo dl consumo di materiali.</span><span class="sxs-lookup"><span data-stu-id="bb178-111">In the **Formula** field, you can set up various formulas for calculating material consumption.</span></span> <span data-ttu-id="bb178-112">Se si utilizza il valore predefinito **Standard**, il consumo non viene calcolato da una formula.</span><span class="sxs-lookup"><span data-stu-id="bb178-112">If you use the default value, **Standard**, the consumption isn't calculated from a formula.</span></span> <span data-ttu-id="bb178-113">Le formule seguenti utilizzano i campi **Altezza**, **Larghezza**, **Profondità**, **Densità** e **Costante**:</span><span class="sxs-lookup"><span data-stu-id="bb178-113">The following formulas work together with the **Height**, **Width**, **Depth**, **Density**, and **Constant** fields:</span></span>

-   <span data-ttu-id="bb178-114">Altezza \* Costante</span><span class="sxs-lookup"><span data-stu-id="bb178-114">Height \* Constant</span></span>
-   <span data-ttu-id="bb178-115">Altezza \* Larghezza \* Costante</span><span class="sxs-lookup"><span data-stu-id="bb178-115">Height \* Width \* Constant</span></span>
-   <span data-ttu-id="bb178-116">Altezza \* Larghezza \* Profondità \* Costante</span><span class="sxs-lookup"><span data-stu-id="bb178-116">Height \* Width \* Depth \* Constant</span></span>
-   <span data-ttu-id="bb178-117">(Altezza \* Larghezza \* Profondità / Densità) \* Costante</span><span class="sxs-lookup"><span data-stu-id="bb178-117">(Height \* Width \* Depth / Density) \* Constant</span></span>

## <a name="rounding-up-and-multiples"></a><span data-ttu-id="bb178-118">Arrotondamento per eccesso e multipli</span><span class="sxs-lookup"><span data-stu-id="bb178-118">Rounding up and multiples</span></span>
<span data-ttu-id="bb178-119">I campi **Arrotondamento per eccesso** e **Multipli** consentono di arrotondare il valore del consumo materiali.</span><span class="sxs-lookup"><span data-stu-id="bb178-119">Together, the **Rounding up** and **Multiples** fields let you round up the material consumption value.</span></span> <span data-ttu-id="bb178-120">Ad esempio, è possibile arrotondare il valore in base all'unità movimentazione in cui le materie prime vengono prelevate per la produzione.</span><span class="sxs-lookup"><span data-stu-id="bb178-120">For example, you can round up the value according to the handling unit in which the raw material is picked for production.</span></span> <span data-ttu-id="bb178-121">Nel campo **Arrotondamento per eccesso** sono disponibili le seguenti opzioni: **Quantità**, **Misurazione** e **Consumo**.</span><span class="sxs-lookup"><span data-stu-id="bb178-121">The following options are available in the **Rounding up** field: **Quantity**, **Measurement**, and **Consumption**.</span></span>

### <a name="quantity"></a><span data-ttu-id="bb178-122">Quantità</span><span class="sxs-lookup"><span data-stu-id="bb178-122">Quantity</span></span>

<span data-ttu-id="bb178-123">Se si seleziona **Quantità** come meccanismo di arrotondamento per eccesso, la quantità deve essere un multiplo della quantità specificata.</span><span class="sxs-lookup"><span data-stu-id="bb178-123">If you select **Quantity** as the rounding-up mechanism, the quantity must be a multiple of the specified quantity.</span></span> <span data-ttu-id="bb178-124">Se ad esempio sono necessari numeri interi, selezionare **1** nel campo **Multipli**.</span><span class="sxs-lookup"><span data-stu-id="bb178-124">For example, if whole numbers are required, select **1** in the **Multiples** field.</span></span> <span data-ttu-id="bb178-125">I numeri vengono arrotondati per eccesso a una quantità divisibile per 1.</span><span class="sxs-lookup"><span data-stu-id="bb178-125">Numbers are then rounded up to a quantity that is divisible by 1.</span></span>

### <a name="measurement"></a><span data-ttu-id="bb178-126">Misurazione</span><span class="sxs-lookup"><span data-stu-id="bb178-126">Measurement</span></span>

<span data-ttu-id="bb178-127">In genere, si seleziona **Misurazione** come meccanismo di arrotondamento per eccesso quando le materie prime provengono in dimensioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="bb178-127">Typically, you select **Measurement** as the rounding-up mechanism when the raw material comes in specific dimensions.</span></span> <span data-ttu-id="bb178-128">Ad esempio, un pezzo di tubo di metallo di 2 metri è necessario per un prodotto finito e il tubo di metallo viene immagazzinato in lunghezze di 4,5 metri.</span><span class="sxs-lookup"><span data-stu-id="bb178-128">For example, a piece of 2-meter metal tube is required for a finished good, and the metal tube is stored in 4.5-meter lengths.</span></span> <span data-ttu-id="bb178-129">In questo caso, il meccanismo di arrotondamento per eccesso **Misurazione** può essere utilizzato per calcolare il numero tubi di metallo necessari per produrre un numero specifico di pezzi del prodotto finito.</span><span class="sxs-lookup"><span data-stu-id="bb178-129">In this case, the **Measurement** rounding-up mechanism can be used to calculate how many metal tubes are required to produce a specific number of pieces of the finished good.</span></span> <span data-ttu-id="bb178-130">Per questo esempio, il campo **Formula** è impostato su **Altezza \* Costante**.</span><span class="sxs-lookup"><span data-stu-id="bb178-130">For this example, the **Formula** field is set to **Height \* Constant**.</span></span> <span data-ttu-id="bb178-131">Il campo **Altezza** è impostato su **2** per indicatore la lunghezza del tubo necessario per il prodotto finito.</span><span class="sxs-lookup"><span data-stu-id="bb178-131">The **Height** field is set to **2** to indicate the length of the tube that is required for the finished good.</span></span> <span data-ttu-id="bb178-132">Il campo **Multiplo** è impostato su **4,5** per indicare che il tubo viene prelevato in lunghezze di 4,5 metri.</span><span class="sxs-lookup"><span data-stu-id="bb178-132">The **Multiple** field is set to **4.5** to indicate that the tube is picked in lengths of 4.5 meters.</span></span> <span data-ttu-id="bb178-133">Questo è il calcolo:</span><span class="sxs-lookup"><span data-stu-id="bb178-133">Here is the calculation:</span></span>

1.  <span data-ttu-id="bb178-134">Numero di multipli necessari per 10 pezzi del prodotto finito: 10 ÷ 2 = 5 pezzi</span><span class="sxs-lookup"><span data-stu-id="bb178-134">Number of multiples that are required for 10 pieces of the finished good: 10 ÷ 2 = 5 pieces</span></span>
2.  <span data-ttu-id="bb178-135">Consumo totale: metri 4,5 × 5 = 22,5 di tubo di metallo</span><span class="sxs-lookup"><span data-stu-id="bb178-135">Total consumption:  4.5 × 5 = 22.5 meters of metal tube</span></span>

<span data-ttu-id="bb178-136">Si presume che 0,5 metri di tubo vengano scartati per ogni cinque pezzi di tubo utilizzati.</span><span class="sxs-lookup"><span data-stu-id="bb178-136">It's assumed that 0.5 meter of tube is scrapped for every five pieces of tube that are consumed.</span></span>

### <a name="consumption"></a><span data-ttu-id="bb178-137">Consumo</span><span class="sxs-lookup"><span data-stu-id="bb178-137">Consumption</span></span>

<span data-ttu-id="bb178-138">In genere, si seleziona**Consumo** come meccanismo di arrotondamento per eccesso quando le materie prime devono essere prelevate nelle quantità intere di unità movimentazione specifica del prodotto.</span><span class="sxs-lookup"><span data-stu-id="bb178-138">Typically, you select **Consumption** as the rounding-up mechanism when raw material must be picked in whole quantities of a specific handling unit of the product.</span></span> <span data-ttu-id="bb178-139">Ad esempio, 2 litri di vernice vengono utilizzati per produrre un pezzo di un prodotto finito e la vernice viene prelevata in latte da 25 litri.</span><span class="sxs-lookup"><span data-stu-id="bb178-139">For example, 2 quarts of paint are used to produce one piece of a finished good, and the paint is picked in 25-quart cans.</span></span> <span data-ttu-id="bb178-140">In questo caso, il meccanismo di arrotondamento per eccesso **Consumo** può essere utilizzato per arrotondare per eccesso il consumo ai numeri interi di latte da 25 litri.</span><span class="sxs-lookup"><span data-stu-id="bb178-140">In this case, the **Consumption** rounding-up mechanism can be used to round up consumption to whole numbers of 25-quart cans.</span></span> <span data-ttu-id="bb178-141">Questo è il calcolo della quantità di vernice necessaria se devono essere prodotti 180 pezzi del prodotto finito:</span><span class="sxs-lookup"><span data-stu-id="bb178-141">Here is the calculation for the amount of paint that is required if 180 pieces of the finished good must be produced:</span></span>

1.  <span data-ttu-id="bb178-142">Vernice necessaria, esclusi scarti: 180 × 2 = 360 litri</span><span class="sxs-lookup"><span data-stu-id="bb178-142">Paint that is required, excluding scrap: 180 × 2 = 360 quarts</span></span>
2.  <span data-ttu-id="bb178-143">Numero di latte: 360 ÷ 25 = 14,4, che viene arrotondato per eccesso a 15</span><span class="sxs-lookup"><span data-stu-id="bb178-143">Number of cans: 360 ÷ 25 = 14.4, which is rounded up to 15</span></span>
3.  <span data-ttu-id="bb178-144">Vernice necessaria, inclusi scarti: 15 × 25 = 375 litri</span><span class="sxs-lookup"><span data-stu-id="bb178-144">Paint that is required, including scrap: 15 × 25 = 375 quarts</span></span>

## <a name="step-consumption"></a><span data-ttu-id="bb178-145">Consumo fase</span><span class="sxs-lookup"><span data-stu-id="bb178-145">Step consumption</span></span>
<span data-ttu-id="bb178-146">Il consumo per fasi viene utilizzato per calcolare il consumo costante in intervalli di quantità.</span><span class="sxs-lookup"><span data-stu-id="bb178-146">Step consumption is used to calculate constant consumption in quantity intervals.</span></span> <span data-ttu-id="bb178-147">Se si seleziona **Consumo fase** nel campo **Formula** della scheda **Impostazioni**, è possibile aggiungere le informazioni sulle fasi nella scheda **Consumo fase**. La quantità utilizzata fissa può essere impostata in intervalli della quantità prodotta.</span><span class="sxs-lookup"><span data-stu-id="bb178-147">If you select **Step consumption** in the **Formula** field on the **Setup** tab, you can add information about the steps on the **Step consumption** tab. The fixed consumed quantity can be set up in intervals of the produced quantity.</span></span> <span data-ttu-id="bb178-148">Ad esempio, il consumo per fasi è impostato come illustrato nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="bb178-148">For example, step consumption is set up as shown in the following table.</span></span>

| <span data-ttu-id="bb178-149">Da serie</span><span class="sxs-lookup"><span data-stu-id="bb178-149">From series</span></span> | <span data-ttu-id="bb178-150">Quantità</span><span class="sxs-lookup"><span data-stu-id="bb178-150">Quantity</span></span> |
|-------------|----------|
| <span data-ttu-id="bb178-151">0,00</span><span class="sxs-lookup"><span data-stu-id="bb178-151">0.00</span></span>        | <span data-ttu-id="bb178-152">10,0000</span><span class="sxs-lookup"><span data-stu-id="bb178-152">10.0000</span></span>  |
| <span data-ttu-id="bb178-153">100,00</span><span class="sxs-lookup"><span data-stu-id="bb178-153">100.00</span></span>      | <span data-ttu-id="bb178-154">20,0000</span><span class="sxs-lookup"><span data-stu-id="bb178-154">20.0000</span></span>  |
| <span data-ttu-id="bb178-155">200,00</span><span class="sxs-lookup"><span data-stu-id="bb178-155">200.00</span></span>      | <span data-ttu-id="bb178-156">40,0000</span><span class="sxs-lookup"><span data-stu-id="bb178-156">40.0000</span></span>  |

<span data-ttu-id="bb178-157">La quantità nella distinta base (DBA) è 1 e la quantità di produzione è 110.</span><span class="sxs-lookup"><span data-stu-id="bb178-157">The bill of materials (BOM) quantity is 1, and the production quantity is 110.</span></span> <span data-ttu-id="bb178-158">La formula per il calcolo del consumo è  Da serie (Quantità) = Consumo.</span><span class="sxs-lookup"><span data-stu-id="bb178-158">The formula for the consumption is From series (Quantity) = Consumption.</span></span> <span data-ttu-id="bb178-159">Poiché la quantità di produzione è 110, rientra nella formula "Da 100 serie".</span><span class="sxs-lookup"><span data-stu-id="bb178-159">Because the production quantity is 110, it falls into the "From 100 series."</span></span> <span data-ttu-id="bb178-160">Pertanto la quantità è 20.</span><span class="sxs-lookup"><span data-stu-id="bb178-160">Therefore, the quantity is 20.</span></span>




