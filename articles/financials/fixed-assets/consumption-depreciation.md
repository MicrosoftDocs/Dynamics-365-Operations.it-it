---
title: Ammortamento del consumo
description: Questo articolo fornisce una panoramica del metodo di ammortamento basato su consumo.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 13751
ms.assetid: d25a681f-49a5-4bfc-aa76-1c6373e35dd8
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: c0f64fee275f63a3e6b31a196df872e41c84dde6
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---

# <a name="consumption-depreciation"></a><span data-ttu-id="4a7e2-103">Ammortamento del consumo</span><span class="sxs-lookup"><span data-stu-id="4a7e2-103">Consumption depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4a7e2-104">Questo articolo fornisce una panoramica del metodo di ammortamento basato su consumo.</span><span class="sxs-lookup"><span data-stu-id="4a7e2-104">This article gives an overview of the Consumption method of depreciation.</span></span>

<span data-ttu-id="4a7e2-105">Quando si imposta un profilo di ammortamento per i cespiti e si seleziona l'opzione **Consumo** nel campo **Metodo** della pagina **Profili di ammortamento**, l'assegnazione dei cespiti al profilo di ammortamento è basata sul loro utilizzo.</span><span class="sxs-lookup"><span data-stu-id="4a7e2-105">If you set up a depreciation profile for fixed assets and select **Consumption** in the **Method** field on the **Depreciation profiles** page, fixed assets are assigned to the depreciation profile based on their usage.</span></span> <span data-ttu-id="4a7e2-106">Non è necessario impostare le percentuali e gli intervalli nella pagina **Profili di ammortamento**.</span><span class="sxs-lookup"><span data-stu-id="4a7e2-106">You don't have to set up percentages and intervals on the **Depreciation profiles** page.</span></span> <span data-ttu-id="4a7e2-107">Dopo avere creato un profilo di ammortamento che utilizza il metodo Consumo, è possibile impostare il metodo in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="4a7e2-107">After you create a depreciation profile that uses the Consumption method, you can set up the method in various ways.</span></span>

## <a name="set-up-and-use-consumption-depreciation"></a><span data-ttu-id="4a7e2-108">Impostare l'ammortamento del consumo</span><span class="sxs-lookup"><span data-stu-id="4a7e2-108">Set up and use consumption depreciation</span></span>
1.  <span data-ttu-id="4a7e2-109">Nella pagina **Profili di ammortamento**, creare il profilo di ammortamento.</span><span class="sxs-lookup"><span data-stu-id="4a7e2-109">On the **Depreciation profiles** page, create the depreciation profile.</span></span> <span data-ttu-id="4a7e2-110">Per i calcoli del consumo, il profilo di ammortamento deve avere un ID e un nome e **Consumo** deve essere selezionato nel campo **Metodo**.</span><span class="sxs-lookup"><span data-stu-id="4a7e2-110">For consumption calculations, the depreciation profile must have an ID and a name, and **Consumption** must be selected in the **Method** field.</span></span>
2.  <span data-ttu-id="4a7e2-111">Nella pagina **Fattori di consumo**, impostare i fattori di consumo.</span><span class="sxs-lookup"><span data-stu-id="4a7e2-111">On the **Consumption factors** page, set up consumption factors.</span></span> <span data-ttu-id="4a7e2-112">Ogni fattore di consumo deve avere un ID e un nome e un fattore di consumo specificato come percentuale o quantità.</span><span class="sxs-lookup"><span data-stu-id="4a7e2-112">Each consumption factor must have an ID and a name, and a consumption factor that is specified as either a quantity or a percentage.</span></span>
3.  <span data-ttu-id="4a7e2-113">Nella pagina **Unità di consumo**, impostare le unità di consumo.</span><span class="sxs-lookup"><span data-stu-id="4a7e2-113">On the **Consumption units** page, set up consumption units.</span></span> <span data-ttu-id="4a7e2-114">Ogni unità di consumo deve avere un ID e un nome.</span><span class="sxs-lookup"><span data-stu-id="4a7e2-114">Each consumption unit must have an ID and a name.</span></span> <span data-ttu-id="4a7e2-115">Le unità di ammortamento vengono utilizzate per calcolare l'ammortamento basato sul consumo nella pagina **Ammortamento consumo**.</span><span class="sxs-lookup"><span data-stu-id="4a7e2-115">Depreciation units are used to calculate consumption depreciation on the **Consumption depreciation** page.</span></span> <span data-ttu-id="4a7e2-116">Esempi di unità sono chilometro (km), chilogrammo (kg) e ora.</span><span class="sxs-lookup"><span data-stu-id="4a7e2-116">Examples of units are kilometer (km), kilogram (kg), and hour.</span></span>
4.  <span data-ttu-id="4a7e2-117">Nella pagina **Cespiti**, impostare i singoli cespiti.</span><span class="sxs-lookup"><span data-stu-id="4a7e2-117">On the **Fixed assets** page, set up individual fixed assets.</span></span> <span data-ttu-id="4a7e2-118">Per ogni cespite, selezionare modelli di valore e registri beni ammortizzabili con profili di ammortamento.</span><span class="sxs-lookup"><span data-stu-id="4a7e2-118">For each fixed asset, select value models and depreciation books that have depreciation profiles.</span></span> <span data-ttu-id="4a7e2-119">È necessario impostare i modelli di valore o i registri beni ammortizzabili per l'ammortamento del consumo, se si hanno cespiti che utilizzano i profili di ammortamento in base al metodo di Consumo.</span><span class="sxs-lookup"><span data-stu-id="4a7e2-119">You must set up value models or depreciation books for consumption depreciation if any of your fixed assets use depreciation profiles that are based on the Consumption method.</span></span> <span data-ttu-id="4a7e2-120">Questa impostazione viene effettuata nella scheda **Ammortamento** della pagina **Modelli di valore** o nella scheda dettaglio **Generale** della pagina **Profilo di ammortamento**.</span><span class="sxs-lookup"><span data-stu-id="4a7e2-120">This setup is done either on the **Depreciation** tab of the **Value models** page or on the **General** FastTab of the **Depreciation profile** page.</span></span> <span data-ttu-id="4a7e2-121">È possibile utilizzare lo stesso modello di valore per più cespiti.</span><span class="sxs-lookup"><span data-stu-id="4a7e2-121">You can use the same value model for multiple fixed assets.</span></span> <span data-ttu-id="4a7e2-122">I profili di ammortamento fanno parte del modello di valore o del registro beni ammortizzabili selezionato per ogni cespite.</span><span class="sxs-lookup"><span data-stu-id="4a7e2-122">Depreciation profiles are part of the value model or depreciation book that you select for each fixed asset.</span></span> <span data-ttu-id="4a7e2-123">Non è possibile aggiungere o modificare profili di ammortamento direttamente nella pagina **Cespiti**.</span><span class="sxs-lookup"><span data-stu-id="4a7e2-123">You can't add or modify depreciation profiles directly on the **Fixed assets** page.</span></span> <span data-ttu-id="4a7e2-124">È possibile modificare i profili di ammortamento solo nella pagina **Registri beni ammortizzabili**.</span><span class="sxs-lookup"><span data-stu-id="4a7e2-124">You can modify depreciation profiles only on the **Depreciation books** page.</span></span>
5.  <span data-ttu-id="4a7e2-125">Nella pagina **Modelli di valore** o **Registro beni ammortizzabili** immettere le informazioni nei seguenti campi del gruppo di campi **Ammortamento consumo**:</span><span class="sxs-lookup"><span data-stu-id="4a7e2-125">On the **Value models** page or the **Depreciation books** page, in the **Consumption depreciation** field group, enter information in the following fields:</span></span>
    -   <span data-ttu-id="4a7e2-126">Fattore di consumo</span><span class="sxs-lookup"><span data-stu-id="4a7e2-126">Consumption factor</span></span>
    -   <span data-ttu-id="4a7e2-127">Unità</span><span class="sxs-lookup"><span data-stu-id="4a7e2-127">Unit</span></span>
    -   <span data-ttu-id="4a7e2-128">Ammortamento unità</span><span class="sxs-lookup"><span data-stu-id="4a7e2-128">Unit depreciation</span></span>
    -   <span data-ttu-id="4a7e2-129">Consumo stimato</span><span class="sxs-lookup"><span data-stu-id="4a7e2-129">Estimated consumption</span></span>

    <span data-ttu-id="4a7e2-130">Nel campo**Consumo registrato** è indicato l'ammortamento basato sul consumo, in unità, già registrato per la combinazione di cespite e modello di valore o per il registro beni ammortizzabili.</span><span class="sxs-lookup"><span data-stu-id="4a7e2-130">The **Posted consumption** field shows the consumption depreciation, in units, that has already been posted either for the combination of the fixed asset and value model, or for the depreciation book.</span></span> <span data-ttu-id="4a7e2-131">Non è possibile aggiornare manualmente il valore del campo.</span><span class="sxs-lookup"><span data-stu-id="4a7e2-131">You can't manually update the value in this field.</span></span>

## <a name="examples"></a><span data-ttu-id="4a7e2-132">Esempi</span><span class="sxs-lookup"><span data-stu-id="4a7e2-132">Examples</span></span>
### <a name="example-1"></a><span data-ttu-id="4a7e2-133">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="4a7e2-133">Example 1</span></span>

<span data-ttu-id="4a7e2-134">Viene impostato il seguente fattore di consumo per il 31 gennaio:</span><span class="sxs-lookup"><span data-stu-id="4a7e2-134">The following consumption factor is set up for January 31:</span></span>

-   <span data-ttu-id="4a7e2-135">La quantità è 1.000.</span><span class="sxs-lookup"><span data-stu-id="4a7e2-135">The quantity is 1,000.</span></span>
-   <span data-ttu-id="4a7e2-136">Il prezzo di ammortamento di unità specificato per il cespite è 1,5.</span><span class="sxs-lookup"><span data-stu-id="4a7e2-136">The unit depreciation price that is specified for the fixed asset is 1.5.</span></span>

<span data-ttu-id="4a7e2-137">La proposta di ammortamento il 31 gennaio è la seguente: I × 1,5 = 1.500 di ammortamento di unità × quantità di 1.000 se il fattore specificato per il cespite è un fattore percentuale, la quantità che viene stimata **Consumo stimato** nel campo per il modello di valore del cespite verranno invece moltiplicati per la percentuale impostata per la data di fine selezionata.</span><span class="sxs-lookup"><span data-stu-id="4a7e2-137">The depreciation proposal on January 31 is as follows: Quantity × Unit depreciation 1,000 × 1.5 = 1,500 If the factor that is specified for the fixed asset is a percentage factor, the quantity that is estimated in the **Estimated consumption** field for the value model of the fixed asset is multiplied by the percentage that is set up for the selected end date.</span></span> <span data-ttu-id="4a7e2-138">Questa quantità verrà suggerita come quantità di ammortamento per il periodo.</span><span class="sxs-lookup"><span data-stu-id="4a7e2-138">The resulting quantity is then suggested as the depreciation quantity for the period.</span></span>

### <a name="example-2"></a><span data-ttu-id="4a7e2-139">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="4a7e2-139">Example 2</span></span>

<span data-ttu-id="4a7e2-140">Viene impostato il seguente fattore di ammortamento basato sul consumo per il 31 gennaio:</span><span class="sxs-lookup"><span data-stu-id="4a7e2-140">The following factor for consumption depreciation is set up for January 31:</span></span>

-   <span data-ttu-id="4a7e2-141">La percentuale è 10%.</span><span class="sxs-lookup"><span data-stu-id="4a7e2-141">The percentage is 10 percent.</span></span>
-   <span data-ttu-id="4a7e2-142">Il prezzo di ammortamento di unità specificato per il cespite è 1,5.</span><span class="sxs-lookup"><span data-stu-id="4a7e2-142">The unit depreciation price that is specified for the fixed asset is 1.5.</span></span>
-   <span data-ttu-id="4a7e2-143">La quantità stimata del cespite è 2.000.</span><span class="sxs-lookup"><span data-stu-id="4a7e2-143">The estimated quantity of the fixed asset is 2,000.</span></span>

<span data-ttu-id="4a7e2-144">La proposta di ammortamento il 31 gennaio è la seguente: Quantità stimata × Percentuale x Ammortamento unità 2.000 × ,10 × 1,5 = 300</span><span class="sxs-lookup"><span data-stu-id="4a7e2-144">The depreciation proposal on January 31 is as follows: Estimated quantity × Percentage × Unit depreciation 2,000 × .10 × 1.5 = 300</span></span>




