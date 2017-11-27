---
title: Ammortamento a saldi decrescenti
description: Questo articolo offre una panoramica del metodo di ammortamento a saldi decrescenti.
author: twheeloc
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 3281
ms.assetid: 1b86763d-d47c-4a6a-a9a6-d97a736750da
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 29bc8cd02d98479197d7e5f5664b9859c03893b3
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="reduce-balance-depreciation"></a><span data-ttu-id="778b2-103">Ammortamento a saldi decrescenti</span><span class="sxs-lookup"><span data-stu-id="778b2-103">Reduce balance depreciation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="778b2-104">Questo articolo offre una panoramica del metodo di ammortamento a saldi decrescenti.</span><span class="sxs-lookup"><span data-stu-id="778b2-104">This article gives an overview of the Reducing balance method of depreciation.</span></span>

<span data-ttu-id="778b2-105">Quando si imposta un profilo di ammortamento cespiti e si seleziona A saldi decrescenti nel campo Metodo della pagina Profili di ammortamento, ai cespiti a cui è assegnato questo profilo verrà applicata la stessa percentuale di ammortamento in ciascun periodo di ammortamento.</span><span class="sxs-lookup"><span data-stu-id="778b2-105">When you set up a fixed asset depreciation profile and select Reducing balance in the Method field in the Depreciation profiles page, the assets that have this depreciation profile assigned to them are depreciated by the same percentage in each depreciation period.</span></span>

<span data-ttu-id="778b2-106">Per impostare l'ammortamento a saldi decrescenti, è necessario anche effettuare selezioni nei campi della scheda dettaglio Generale della pagina Profili di ammortamento.</span><span class="sxs-lookup"><span data-stu-id="778b2-106">To set up reducing balance depreciation, you must also make selections in fields on the General FastTab of the Depreciation profiles page.</span></span> <span data-ttu-id="778b2-107">Selezionare innanzitutto un anno nel campo Anno di ammortamento.</span><span class="sxs-lookup"><span data-stu-id="778b2-107">First, select a year in the Depreciation year field.</span></span> <span data-ttu-id="778b2-108">Le opzioni visualizzate nel campo Frequenza periodo dipendono dalla selezione effettuata nel campo precedente, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="778b2-108">Depending on the selection, different options appear in the Period frequency field, as explained in the following sections.</span></span> 

<span data-ttu-id="778b2-109">È inoltre necessario immettere un valore nel campo Percentuale relativo al profilo di ammortamento.</span><span class="sxs-lookup"><span data-stu-id="778b2-109">You must also enter a value in the Percentage field for the depreciation profile.</span></span> <span data-ttu-id="778b2-110">Se si seleziona l'opzione Ammortamento completo, la base di ammortamento rimanente viene rilevata nell'ultimo periodo di ammortamento e l'importo risultante può essere molto elevato.</span><span class="sxs-lookup"><span data-stu-id="778b2-110">If you select the Full depreciation option, the remaining depreciation basis is taken in the last depreciation period and could be a large amount.</span></span> <span data-ttu-id="778b2-111">In alcuni paesi non viene effettuato il passaggio al metodo di ammortamento a quote costanti.</span><span class="sxs-lookup"><span data-stu-id="778b2-111">Some countries/regions do not use a switchover to a straight line method.</span></span> <span data-ttu-id="778b2-112">Il passaggio avviene quando l'importo di tale metodo è maggiore o uguale all'importo del profilo di ammortamento primario e l'importo di ammortamento sottratto costituisce l'importo del metodo alternativo.</span><span class="sxs-lookup"><span data-stu-id="778b2-112">Switchover occurs when the alternative depreciation method amount is greater than or equal to the primary depreciation profile amount, and the depreciation amount taken is the alternative method amount.</span></span> 

<span data-ttu-id="778b2-113">Poiché un cespite non viene mai completamente ammortizzato in base a un calcolo percentuale, per raggiungere questo scopo è necessario selezionare l'opzione Ammortamento completo.</span><span class="sxs-lookup"><span data-stu-id="778b2-113">Because an asset will never be fully depreciated based on a percentage calculation, you must select the Full depreciation option to fully depreciate an asset.</span></span>

## <a name="select-a-depreciation-year"></a><span data-ttu-id="778b2-114">Selezionare un anno di ammortamento</span><span class="sxs-lookup"><span data-stu-id="778b2-114">Select a depreciation year</span></span>
<span data-ttu-id="778b2-115">È possibile selezionare Calendario o Fiscale nel campo Anno di ammortamento della pagina Profili di ammortamento.</span><span class="sxs-lookup"><span data-stu-id="778b2-115">You can select either Calendar or Fiscal in the Depreciation year field in the Depreciation profiles page.</span></span> <span data-ttu-id="778b2-116">In base al valore selezionato verranno definite le opzioni disponibili nel campo Frequenza periodo.</span><span class="sxs-lookup"><span data-stu-id="778b2-116">The selection defines the options that are available in the Period frequency field.</span></span> <span data-ttu-id="778b2-117">L'opzione predefinita è Calendario.</span><span class="sxs-lookup"><span data-stu-id="778b2-117">The default option is Calendar.</span></span>

### <a name="calendar"></a><span data-ttu-id="778b2-118">Calendario</span><span class="sxs-lookup"><span data-stu-id="778b2-118">Calendar</span></span>

<span data-ttu-id="778b2-119">Se si seleziona l'opzione Calendario, la base di ammortamento, che in genere corrisponde alla differenza tra il valore contabile netto e il valore di recupero, verrà aggiornata al 1° gennaio di ogni anno.</span><span class="sxs-lookup"><span data-stu-id="778b2-119">The Calendar option updates the depreciation base, which is typically the net book value minus the scrap value, on January 1 of each year.</span></span> <span data-ttu-id="778b2-120">Nell'esempio relativo all'ammortamento a saldi decrescenti illustrato più avanti in questo argomento, la base di ammortamento corrisponde al numeratore della prima espressione riportata nella colonna relativa ai calcoli.</span><span class="sxs-lookup"><span data-stu-id="778b2-120">In the reducing balance depreciation example later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="778b2-121">Se si seleziona Calendario, nel campo Frequenza periodo, che consente di definire gli importi e le date di registrazione dei ratei di ammortamento per l'anno di calendario, saranno disponibili le seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="778b2-121">If you select Calendar, the following options are available in the Period frequency field, which defines the depreciation accrual posting dates and amounts throughout the calendar year:</span></span>

-   <span data-ttu-id="778b2-122">Annuale: la registrazione viene eseguita il 31 dicembre.</span><span class="sxs-lookup"><span data-stu-id="778b2-122">Yearly posts on December 31.</span></span>
-   <span data-ttu-id="778b2-123">Mensile: viene registrato un importo mensile alla fine di ciascun mese di calendario.</span><span class="sxs-lookup"><span data-stu-id="778b2-123">Monthly posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="778b2-124">Trimestrale: viene registrato un importo trimestrale alla fine di ciascun trimestre di calendario (31 marzo, 30 giugno, 30 settembre e 31 dicembre).</span><span class="sxs-lookup"><span data-stu-id="778b2-124">Quarterly posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="778b2-125">Semestrale: viene registrato un importo semestrale alla fine di ciascun semestre di calendario (30 giugno e 31 dicembre).</span><span class="sxs-lookup"><span data-stu-id="778b2-125">Half-Yearly posts a half-yearly amount at the end of each calendar half-year (June 30 and December 31).</span></span>
-   <span data-ttu-id="778b2-126">Giornaliero: viene registrato l'importo di ammortamento per il metodo di ammortamento giornaliero mediante una sola transazione giornaliera.</span><span class="sxs-lookup"><span data-stu-id="778b2-126">Daily posts the depreciation amount for the daily depreciation method using one transaction for each day.</span></span>

<span data-ttu-id="778b2-127">Se ad esempio si seleziona Annuale, l'ammortamento annuale viene registrato una sola volta, il 31 dicembre di ciascun anno.</span><span class="sxs-lookup"><span data-stu-id="778b2-127">For example, if you select Yearly, the yearly depreciation is posted only one time, on December 31 of each year.</span></span> <span data-ttu-id="778b2-128">Se si seleziona Mensile, l'ammortamento mensile viene registrato ogni mese ed è uguale a 1/12 dell'importo dell'ammortamento annuale.</span><span class="sxs-lookup"><span data-stu-id="778b2-128">If you select Monthly, the monthly depreciation is posted each month as 1/12 of the yearly depreciation amount.</span></span>

### <a name="fiscal"></a><span data-ttu-id="778b2-129">Fiscale</span><span class="sxs-lookup"><span data-stu-id="778b2-129">Fiscal</span></span>

<span data-ttu-id="778b2-130">Se si seleziona Fiscale nel campo Anno di ammortamento, viene utilizzato il metodo di ammortamento a quote costanti.</span><span class="sxs-lookup"><span data-stu-id="778b2-130">If you select Fiscal in the Depreciation year field, the straight line depreciation method is used.</span></span> <span data-ttu-id="778b2-131">Viene calcolato in base all'anno fiscale, impostato nella pagina Calendari fiscali per il calendario fiscale selezionato nella pagina Contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="778b2-131">It is calculated based on the fiscal year, which is set up in the Fiscal calendars page for the fiscal calendar that is selected in the Ledger page.</span></span> <span data-ttu-id="778b2-132">Se ad esempio l'anno fiscale inizia il 1° luglio e termina il 30 giugno, il calcolo dell'ammortamento inizia il 1° luglio.</span><span class="sxs-lookup"><span data-stu-id="778b2-132">For example, for fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="778b2-133">La durata dell'anno fiscale non deve essere necessariamente di 12 mesi.</span><span class="sxs-lookup"><span data-stu-id="778b2-133">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="778b2-134">L'ammortamento viene rettificato per ciascun periodo fiscale.</span><span class="sxs-lookup"><span data-stu-id="778b2-134">The depreciation is adjusted for each fiscal period.</span></span> <span data-ttu-id="778b2-135">La durata dell'anno fiscale successivo si basa sui periodi fiscali impostati durante la creazione di un nuovo anno fiscale nella pagina Calendari fiscali.</span><span class="sxs-lookup"><span data-stu-id="778b2-135">The length of the next fiscal year is based on the fiscal periods that you set up when you create a new fiscal year in the Fiscal calendars page.</span></span>


<span data-ttu-id="778b2-136">Se si seleziona Fiscale nel campo Frequenza periodo sono disponibili le seguenti opzioni di frequenza del periodo:</span><span class="sxs-lookup"><span data-stu-id="778b2-136">If you select Fiscal, the following options are available in the Period frequency field:</span></span>

-   <span data-ttu-id="778b2-137">Annuale: l'importo totale dell'ammortamento calcolato per l'anno fiscale viene registrato come importo unico nell'ultimo giorno dell'anno fiscale.</span><span class="sxs-lookup"><span data-stu-id="778b2-137">Yearly posts the total amount of the depreciation calculated for the fiscal year as one amount on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="778b2-138">In Periodo fiscale viene registrato l'importo totale dell'ammortamento calcolato per l'anno fiscale, che viene attribuito ai periodi fiscali definiti per il calendario fiscale selezionato nella pagina Contabilità generale o per il calendario fiscale selezionato per il libro per il cespite.</span><span class="sxs-lookup"><span data-stu-id="778b2-138">Fiscal period posts the total amount of the depreciation calculated for the fiscal year, which is accrued into the fiscal periods that are defined for the fiscal calendar that is selected in the Ledger page, or for the fiscal calendar that is selected for the book for a fixed asset.</span></span>

## <a name="example-of-reducing-balance-depreciation"></a><span data-ttu-id="778b2-139">Esempio di ammortamento a saldi decrescenti</span><span class="sxs-lookup"><span data-stu-id="778b2-139">Example of reducing balance depreciation</span></span>

<span data-ttu-id="778b2-140">Si supponga che il prezzo di acquisizione di un cespite sia 11.000, il valore di scarto 1.000 e il fattore della percentuale ammortamento 30.</span><span class="sxs-lookup"><span data-stu-id="778b2-140">Suppose that the fixed asset acquisition price is 11,000, the scrap value is 1,000, and the depreciation percentage factor is 30.</span></span> 

<span data-ttu-id="778b2-141">Utilizzando il metodo A saldi decrescenti, il 30% della base di ammortamento (valore contabile netto meno valore di scarto) viene calcolato alla fine del periodo di ammortamento precedente.</span><span class="sxs-lookup"><span data-stu-id="778b2-141">Using the Reducing balance method, 30 percent of the depreciation base (net book value minus scrap value) is calculated at the end of the previous depreciation period.</span></span> <span data-ttu-id="778b2-142">L'ammortamento per i primi tre anni viene visualizzato nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="778b2-142">Depreciation for the first three years is shown in the following table.</span></span>

| <span data-ttu-id="778b2-143">Periodo</span><span class="sxs-lookup"><span data-stu-id="778b2-143">Period</span></span> | <span data-ttu-id="778b2-144">Calcolo della quota di ammortamento annuale</span><span class="sxs-lookup"><span data-stu-id="778b2-144">Calculation of yearly depreciation amount</span></span> | <span data-ttu-id="778b2-145">Valore contabile netto alla fine dell'anno</span><span class="sxs-lookup"><span data-stu-id="778b2-145">Net book value at the end of the year</span></span> |
|--------|-------------------------------------------|---------------------------------------|
| <span data-ttu-id="778b2-146">Anno 1</span><span class="sxs-lookup"><span data-stu-id="778b2-146">Year 1</span></span> | <span data-ttu-id="778b2-147">(11.000 - 1.000) \* 30% = 3.000</span><span class="sxs-lookup"><span data-stu-id="778b2-147">(11,000 - 1,000) \* 30% = 3,000</span></span>           | <span data-ttu-id="778b2-148">(11.000 - 1.000) - 3.000 = 7.000</span><span class="sxs-lookup"><span data-stu-id="778b2-148">(11,000 - 1,000) - 3,000 = 7,000</span></span>      |
| <span data-ttu-id="778b2-149">Anno 2</span><span class="sxs-lookup"><span data-stu-id="778b2-149">Year 2</span></span> | <span data-ttu-id="778b2-150">(7.000 - 1.000) \* 30% = 1.800</span><span class="sxs-lookup"><span data-stu-id="778b2-150">(7,000 - 1,000) \* 30% = 1,800</span></span>            | <span data-ttu-id="778b2-151">(7.000 -1.800) = 5.200</span><span class="sxs-lookup"><span data-stu-id="778b2-151">(7,000 -1,800) = 5,200</span></span>                |
| <span data-ttu-id="778b2-152">Anno 3</span><span class="sxs-lookup"><span data-stu-id="778b2-152">Year 3</span></span> | <span data-ttu-id="778b2-153">(5.200 - 1.000) \* 30% = 1.260</span><span class="sxs-lookup"><span data-stu-id="778b2-153">(5,200 - 1,000) \* 30% = 1,260</span></span>            | <span data-ttu-id="778b2-154">(5.200 - 1.260) = 3.940</span><span class="sxs-lookup"><span data-stu-id="778b2-154">(5,200 - 1,260) = 3,940</span></span>               |

 
-






