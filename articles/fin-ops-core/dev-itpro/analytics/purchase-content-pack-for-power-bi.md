---
title: Contenuto Analisi delle spese di acquisto di Power BI
description: In questo argomento viene descritto cosa è incluso nel contenuto Analisi delle spese di acquisto di Power BI.
author: FrankDahl
ms.date: 04/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchaseSpendAnalysisPowerBI
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: f9741b5f30f5e62b9e80000953113377fe016253
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5749371"
---
# <a name="purchase-spend-analysis-power-bi-content"></a><span data-ttu-id="4a0ae-103">Contenuto Analisi delle spese di acquisto di Power BI</span><span class="sxs-lookup"><span data-stu-id="4a0ae-103">Purchase spend analysis Power BI content</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4a0ae-104">In questo argomento viene descritto cosa è incluso nel contenuto **Analisi delle spese di acquisto** di Microsoft Power BI.</span><span class="sxs-lookup"><span data-stu-id="4a0ae-104">This topic describes what is included in the **Purchase spend analysis** Microsoft Power BI content.</span></span> <span data-ttu-id="4a0ae-105">Descrive come accedere ai report di Power BI e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto.</span><span class="sxs-lookup"><span data-stu-id="4a0ae-105">It explains how to access the Power BI reports, and provides information about the data model and entities that are used to build the content.</span></span>

## <a name="overview"></a><span data-ttu-id="4a0ae-106">Panoramica</span><span class="sxs-lookup"><span data-stu-id="4a0ae-106">Overview</span></span>

<span data-ttu-id="4a0ae-107">Il contenuto di Power BI **Analisi delle spese di acquisto** è stato progettato per consentire ai responsabili acquisti e ai dirigenti responsabili di budget di tenere sotto controllo la spesa di acquisto.</span><span class="sxs-lookup"><span data-stu-id="4a0ae-107">The **Purchase spend analysis** Power BI content was designed to help purchasing managers and managers who are responsible for budgets keep track of purchase spending.</span></span> <span data-ttu-id="4a0ae-108">I responsabili possono analizzare la spesa d'acquisto nei seguenti modi:</span><span class="sxs-lookup"><span data-stu-id="4a0ae-108">Managers can analyze purchase spending in the following ways:</span></span>

- <span data-ttu-id="4a0ae-109">Acquisto da inizio anno (per gruppo di fornitori e singoli fornitori, per categoria di approvvigionamento e singoli prodotti e per ubicazione del fornitore)</span><span class="sxs-lookup"><span data-stu-id="4a0ae-109">Year-to-date purchase (by vendor group and individual vendors, procurement category and individual products, and vendor location)</span></span>
- <span data-ttu-id="4a0ae-110">Modifica di acquisto da inizio anno (per gruppo di fornitori e categoria di approvvigionamento)</span><span class="sxs-lookup"><span data-stu-id="4a0ae-110">Year-over-year purchase change (by vendor group and procurement category)</span></span>

<span data-ttu-id="4a0ae-111">Il contenuto utilizza dati transazionali di acquisto e offre sia una visualizzazione aggregata delle cifre di acquisto a livello di società che una scomposizione dettagliata della spesa di acquisto per fornitore e prodotto.</span><span class="sxs-lookup"><span data-stu-id="4a0ae-111">The content uses purchase transactional data, and provides both an aggregate view of the company-wide purchase figures and a breakdown of purchase spending by vendor and product.</span></span> <span data-ttu-id="4a0ae-112">I report evidenziano le modifiche nella spesa di acquisto nel tempo.</span><span class="sxs-lookup"><span data-stu-id="4a0ae-112">Reports highlight changes in purchase spending over time.</span></span> <span data-ttu-id="4a0ae-113">Di conseguenza, è possibile utilizzarli per avvisare i responsabili sulle tendenze positive e negative di spesa per singoli fornitori e prodotti.</span><span class="sxs-lookup"><span data-stu-id="4a0ae-113">Therefore, the reports can be used to alert managers about positive and negative spending trends for individual vendors and products.</span></span> <span data-ttu-id="4a0ae-114">Inoltre, i grafici mostrano la spesa di acquisto per categorie di approvvigionamento e gruppi di fornitori diversi.</span><span class="sxs-lookup"><span data-stu-id="4a0ae-114">Additionally, charts show purchase spending for different procurement categories and vendor groups.</span></span> <span data-ttu-id="4a0ae-115">Pertanto, i responsabili di categoria e regionali possono usare questi grafici per identificare i cambiamenti nel comportamento di spesa.</span><span class="sxs-lookup"><span data-stu-id="4a0ae-115">Therefore, category and regional managers can use the charts to help identify changes in spending behavior.</span></span>

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="4a0ae-116">Accesso al contenuto Power BI</span><span class="sxs-lookup"><span data-stu-id="4a0ae-116">Accessing the Power BI content</span></span>
<span data-ttu-id="4a0ae-117">Il contenuto di Power BI **Analisi delle spese di acquisto** viene mostrato nella pagina **Analisi di spesa e acquisto** (**Approvvigionamento** \> **Richieste di informazioni e report** \> **Analisi delle prestazioni di acquisto** \> **Analisi delle prestazioni di acquisto**).</span><span class="sxs-lookup"><span data-stu-id="4a0ae-117">The **Purchase spend analysis** Power BI content is shown on the **Purchase and spend analysis** page (**Procurement and sourcing** \> **Inquiries and reports** \> **Purchase performance analysis** \> **Purchase and spend analysis**).</span></span>

## <a name="metrics-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="4a0ae-118">Metriche incluse nel contenuto Power BI</span><span class="sxs-lookup"><span data-stu-id="4a0ae-118">Metrics that are included in the Power BI content</span></span>
<span data-ttu-id="4a0ae-119">Il contenuto di Power BI **Analisi delle spese di acquisto** include un report costituito da un set di metriche.</span><span class="sxs-lookup"><span data-stu-id="4a0ae-119">The **Purchase spend analysis** Power BI content includes a report that consists of a set of metrics.</span></span> <span data-ttu-id="4a0ae-120">Queste metriche vengono visualizzate come grafici, riquadri e tabelle.</span><span class="sxs-lookup"><span data-stu-id="4a0ae-120">These metrics are visualized as charts, tiles, and tables.</span></span> 

<span data-ttu-id="4a0ae-121">Nelle seguenti sezioni viene fornita una panoramica delle visualizzazioni.</span><span class="sxs-lookup"><span data-stu-id="4a0ae-121">The following sections provide an overview of the visualizations.</span></span>

### <a name="purchase-by-vendor-report-page"></a><span data-ttu-id="4a0ae-122">Pagina del report sugli acquisti per fornitore</span><span class="sxs-lookup"><span data-stu-id="4a0ae-122">Purchase by vendor report page</span></span>
<span data-ttu-id="4a0ae-123">**Grafici**</span><span class="sxs-lookup"><span data-stu-id="4a0ae-123">**Charts**</span></span>
- <span data-ttu-id="4a0ae-124">Primi 10 fornitori per acquisti (grafico a barre impilate)</span><span class="sxs-lookup"><span data-stu-id="4a0ae-124">Top 10 vendors by purchase (stacked bar chart)</span></span>
- <span data-ttu-id="4a0ae-125">Acquisti totali per gruppo di fornitori/paese/nome (grafico a torta)</span><span class="sxs-lookup"><span data-stu-id="4a0ae-125">Total purchase by vendor group / country / name (pie chart)</span></span>
- <span data-ttu-id="4a0ae-126">Acquisti per gruppo di fornitori/paese/nome (istogramma)</span><span class="sxs-lookup"><span data-stu-id="4a0ae-126">Purchase by vendor group / country / name (column chart)</span></span>
- <span data-ttu-id="4a0ae-127">Media degli acquisti per gruppo di fornitori/paese/nome (istogramma)</span><span class="sxs-lookup"><span data-stu-id="4a0ae-127">Average purchase by vendor group / country / name (column chart)</span></span>

<span data-ttu-id="4a0ae-128">**Riquadri**</span><span class="sxs-lookup"><span data-stu-id="4a0ae-128">**Tiles**</span></span>
- <span data-ttu-id="4a0ae-129">Totale acquisto</span><span class="sxs-lookup"><span data-stu-id="4a0ae-129">Total purchase</span></span>
- <span data-ttu-id="4a0ae-130">Crescita degli acquisti su base annua</span><span class="sxs-lookup"><span data-stu-id="4a0ae-130">YOY purchase growth</span></span>
- <span data-ttu-id="4a0ae-131">N. totale fornitori</span><span class="sxs-lookup"><span data-stu-id="4a0ae-131">Total # vendors</span></span>
- <span data-ttu-id="4a0ae-132">N. totale dei fornitori attivi</span><span class="sxs-lookup"><span data-stu-id="4a0ae-132">Total # of active vendors</span></span>

<span data-ttu-id="4a0ae-133">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="4a0ae-133">**Example**</span></span>
<img src="media/spend1.png" alt="Purchase by vendor">

### <a name="purchase-by-product-report-page"></a><span data-ttu-id="4a0ae-134">Pagina del report sugli acquisti per prodotto</span><span class="sxs-lookup"><span data-stu-id="4a0ae-134">Purchase by product report page</span></span>

<span data-ttu-id="4a0ae-135">**Grafici**</span><span class="sxs-lookup"><span data-stu-id="4a0ae-135">**Charts**</span></span>
- <span data-ttu-id="4a0ae-136">Acquisti per categoria di approvvigionamento/nome prodotto (istogramma)</span><span class="sxs-lookup"><span data-stu-id="4a0ae-136">Purchase by procurement category / product name (column chart)</span></span>
- <span data-ttu-id="4a0ae-137">Acquisti totali per categoria di approvvigionamento/nome prodotto (grafico a torta)</span><span class="sxs-lookup"><span data-stu-id="4a0ae-137">Total purchase by procurement category / product name (pie chart)</span></span>
- <span data-ttu-id="4a0ae-138">Primi 10 prodotti per acquisti (grafico a barre impilate)</span><span class="sxs-lookup"><span data-stu-id="4a0ae-138">Top 10 products by purchase (stacked bar chart)</span></span>

<span data-ttu-id="4a0ae-139">**Riquadri**</span><span class="sxs-lookup"><span data-stu-id="4a0ae-139">**Tiles**</span></span>
- <span data-ttu-id="4a0ae-140">N. totale di prodotti</span><span class="sxs-lookup"><span data-stu-id="4a0ae-140">Total # of products</span></span></li>
- <span data-ttu-id="4a0ae-141">Percentuale di prodotti attivi totali del numero totale di prodotti</span><span class="sxs-lookup"><span data-stu-id="4a0ae-141">Total active products percentage of total # of products</span></span>
- <span data-ttu-id="4a0ae-142">Numero di prodotti che rappresentano l'80% degli acquisti</span><span class="sxs-lookup"><span data-stu-id="4a0ae-142">Number of products accounting for 80% purchase</span></span>

<span data-ttu-id="4a0ae-143">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="4a0ae-143">**Example**</span></span>


<img src="media/purchaseByProduct.png" alt="Purchase by Product">

### <a name="purchase-by-period-report-page"></a><span data-ttu-id="4a0ae-144">Pagina del report sugli acquisti per periodo</span><span class="sxs-lookup"><span data-stu-id="4a0ae-144">Purchase by period report page</span></span>
<span data-ttu-id="4a0ae-145">Questa pagina nostra gli acquisti nell'anno corrente e nell'anno passato e crescita per categoria di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="4a0ae-145">This page shows purchases this year and last year, and growth by procurement category.</span></span>

<span data-ttu-id="4a0ae-146">**Grafici**</span><span class="sxs-lookup"><span data-stu-id="4a0ae-146">**Charts**</span></span> 
- <span data-ttu-id="4a0ae-147">Acquisti al mese/giorno (istogramma)</span><span class="sxs-lookup"><span data-stu-id="4a0ae-147">Purchase by month / day (column chart)</span></span>
- <span data-ttu-id="4a0ae-148">Scostamento di acquisti cumulativi su base annua (grafico a cascata)</span><span class="sxs-lookup"><span data-stu-id="4a0ae-148">Cumulative purchase YOY variance (waterfall chart)</span></span>
- <span data-ttu-id="4a0ae-149">Crescita degli acquisti totali su base annua (istogramma)</span><span class="sxs-lookup"><span data-stu-id="4a0ae-149">Total purchase YOY growth (column chart)</span></span>
- <span data-ttu-id="4a0ae-150">Rendiconto di approvvigionamento (matrice)</span><span class="sxs-lookup"><span data-stu-id="4a0ae-150">Procurement statement (matrix)</span></span>

<span data-ttu-id="4a0ae-151">**Riquadri**</span><span class="sxs-lookup"><span data-stu-id="4a0ae-151">**Tiles**</span></span>
- <span data-ttu-id="4a0ae-152">Crescita degli acquisti su base annua</span><span class="sxs-lookup"><span data-stu-id="4a0ae-152">YOY purchase growth</span></span>
- <span data-ttu-id="4a0ae-153">% di crescita degli acquisti su base annua</span><span class="sxs-lookup"><span data-stu-id="4a0ae-153">YOY purchase growth %</span></span>

<span data-ttu-id="4a0ae-154">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="4a0ae-154">**Example**</span></span>
<img src="media/purchaseByPeriod.png" alt="Purchase by Period">

### <a name="purchase-by-vendor-location-report-page"></a><span data-ttu-id="4a0ae-155">Pagina del report sugli acquisti per ubicazione del fornitore</span><span class="sxs-lookup"><span data-stu-id="4a0ae-155">Purchase by vendor location report page</span></span>

<span data-ttu-id="4a0ae-156">**Grafici**</span><span class="sxs-lookup"><span data-stu-id="4a0ae-156">**Charts**</span></span>
- <span data-ttu-id="4a0ae-157">Acquisti per città</span><span class="sxs-lookup"><span data-stu-id="4a0ae-157">Purchase by city</span></span>
- <span data-ttu-id="4a0ae-158">% di crescita su base annua degli acquisti</span><span class="sxs-lookup"><span data-stu-id="4a0ae-158">Purchase YOY growth %</span></span>
- <span data-ttu-id="4a0ae-159">Acquisti per paese</span><span class="sxs-lookup"><span data-stu-id="4a0ae-159">Purchase by country</span></span>

<span data-ttu-id="4a0ae-160">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="4a0ae-160">**Example**</span></span>
<img src="media/purchByVendorLocation.png" alt="Purchase by Vendor Location">

### <a name="purchase-spend-analysis-by-time-report-page"></a><span data-ttu-id="4a0ae-161">Pagina del report sull'analisi delle spese di acquisto in base all'ora</span><span class="sxs-lookup"><span data-stu-id="4a0ae-161">Purchase spend analysis by time report page</span></span>

<span data-ttu-id="4a0ae-162">**Grafici**</span><span class="sxs-lookup"><span data-stu-id="4a0ae-162">**Charts**</span></span> 
- <span data-ttu-id="4a0ae-163">Acquisti nell'anno corrente al mese/giorno (grafico a linee)</span><span class="sxs-lookup"><span data-stu-id="4a0ae-163">Purchase current year by month / day (line chart)</span></span>
- <span data-ttu-id="4a0ae-164">Acquisti nell'anno corrente e nell'anno passato (grafico a linee e colonne)</span><span class="sxs-lookup"><span data-stu-id="4a0ae-164">Purchase current and last year (line and column chart)</span></span>

<span data-ttu-id="4a0ae-165">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="4a0ae-165">**Example**</span></span>
<img src="media/PurchByTIme.png" alt="Purchase by Time">

### <a name="purchase-spend-analysis-by-vendor-report-page"></a><span data-ttu-id="4a0ae-166">Pagina del report sull'analisi delle spese di acquisto in base fornitore</span><span class="sxs-lookup"><span data-stu-id="4a0ae-166">Purchase spend analysis by vendor report page</span></span>

<span data-ttu-id="4a0ae-167">**Grafici**</span><span class="sxs-lookup"><span data-stu-id="4a0ae-167">**Charts**</span></span> 
- <span data-ttu-id="4a0ae-168">% di acquisti dei primi 10 fornitori (grafico a imbuto)</span><span class="sxs-lookup"><span data-stu-id="4a0ae-168">Top 10 vendor purchase % of purchase (funnel)</span></span>
- <span data-ttu-id="4a0ae-169">Primi 10 fornitori con aumento delle spese su base annua</span><span class="sxs-lookup"><span data-stu-id="4a0ae-169">Top 10 vendors with increased spending YOY</span></span>
- <span data-ttu-id="4a0ae-170">Primi 10 fornitori con diminuzione delle spese su base annua</span><span class="sxs-lookup"><span data-stu-id="4a0ae-170">Top 10 vendors with decreased spending YOY</span></span>

<span data-ttu-id="4a0ae-171">**Esempio** 
</span><span class="sxs-lookup"><span data-stu-id="4a0ae-171">**Example** 
</span></span><img src="media/PurchSpendAnalysisByVendor.png" alt="Purchase spend by vendor">


## <a name="data-model-and-entities"></a><span data-ttu-id="4a0ae-172">Modello dati ed entità</span><span class="sxs-lookup"><span data-stu-id="4a0ae-172">Data model and entities</span></span>
<span data-ttu-id="4a0ae-173">I seguenti dati vengono utilizzati per compilare le pagine di report nel contenuto Power BI **Analisi delle spese di acquisto**.</span><span class="sxs-lookup"><span data-stu-id="4a0ae-173">The following data is used to fill the report pages in the **Purchase spend analysis** Power BI content.</span></span> <span data-ttu-id="4a0ae-174">Questi dati vengono rappresentati come misure aggregate approntate nell'archivio entità.</span><span class="sxs-lookup"><span data-stu-id="4a0ae-174">This data is represented as aggregate measurements that are staged in the Entity store.</span></span> <span data-ttu-id="4a0ae-175">L'archivio entità è un database di Microsoft SQL Server che viene ottimizzato per l'analisi dei dati.</span><span class="sxs-lookup"><span data-stu-id="4a0ae-175">The Entity store is a Microsoft SQL Server database that is optimized for analytics.</span></span> <span data-ttu-id="4a0ae-176">Per ulteriori informazioni, vedere [Integrazione di Power BI con l'archivio entità](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="4a0ae-176">For more information, see [Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span>

<span data-ttu-id="4a0ae-177">Le misure di aggregazione in questo pacchetto di contenuti sono il sottoinsieme delle misure di aggregazione disponibili nel cubo Acquisiti in Microsoft Dynamics AX 2012 e Microsoft Dynamics AX 2012 R3.</span><span class="sxs-lookup"><span data-stu-id="4a0ae-177">The aggregate measurements in this content are the subset of aggregate measurements that were available in the Purchase Cube in Microsoft Dynamics AX 2012 and Microsoft Dynamics AX 2012 R3.</span></span> <span data-ttu-id="4a0ae-178">Per rappresentare le misure di aggregazione del cubo nell'Archivio entità, è necessario renderle distribuibili.</span><span class="sxs-lookup"><span data-stu-id="4a0ae-178">To stage the cube's aggregate measurements in the Entity store, you must make them deployable.</span></span> <span data-ttu-id="4a0ae-179">Per ulteriori informazioni, vedere la procedura per la rappresentazione delle misure di aggregazione nell'Archivio entità in [Integrazione di Power BI con l'archivio entità](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="4a0ae-179">For more information, see the procedure for staging aggregate measurements in the Entity store in [Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span> <span data-ttu-id="4a0ae-180">Le seguenti misure di aggregazione chiave sono disponibili direttamente dall'entità delle righe della fattura e sono utilizzate come base del contenuto.</span><span class="sxs-lookup"><span data-stu-id="4a0ae-180">The following key aggregate measurements are available directly from the Invoice lines entity and are used as the basis of the content.</span></span>

| <span data-ttu-id="4a0ae-181">Entità</span><span class="sxs-lookup"><span data-stu-id="4a0ae-181">Entity</span></span>        | <span data-ttu-id="4a0ae-182">Misure di aggregazione chiave</span><span class="sxs-lookup"><span data-stu-id="4a0ae-182">Key aggregate measurements</span></span> | <span data-ttu-id="4a0ae-183">Origine dati</span><span class="sxs-lookup"><span data-stu-id="4a0ae-183">Data source</span></span>                                 | <span data-ttu-id="4a0ae-184">Campo</span><span class="sxs-lookup"><span data-stu-id="4a0ae-184">Field</span></span>              | <span data-ttu-id="4a0ae-185">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a0ae-185">Description</span></span>                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| <span data-ttu-id="4a0ae-186">Righe fattura</span><span class="sxs-lookup"><span data-stu-id="4a0ae-186">Invoice lines</span></span> | <span data-ttu-id="4a0ae-187">Acquisti</span><span class="sxs-lookup"><span data-stu-id="4a0ae-187">Purchase</span></span>                   | <span data-ttu-id="4a0ae-188">VendInvoiceTrans</span><span class="sxs-lookup"><span data-stu-id="4a0ae-188">VendInvoiceTrans</span></span>                            | <span data-ttu-id="4a0ae-189">SUM(LineAmountMST)</span><span class="sxs-lookup"><span data-stu-id="4a0ae-189">SUM(LineAmountMST)</span></span> | <span data-ttu-id="4a0ae-190">Importo nella valuta di contabilizzazione.</span><span class="sxs-lookup"><span data-stu-id="4a0ae-190">The amount in the accounting currency.</span></span> |

<span data-ttu-id="4a0ae-191">Nella seguente tabella vengono illustrate le misurazioni chiave nel contenuto calcolate dall'entità delle righe della fattura.</span><span class="sxs-lookup"><span data-stu-id="4a0ae-191">The following table shows the key measurements in the content that are calculated from the Invoice lines entity.</span></span>

| <span data-ttu-id="4a0ae-192">Unità di misura</span><span class="sxs-lookup"><span data-stu-id="4a0ae-192">Measure</span></span>               | <span data-ttu-id="4a0ae-193">Calcolo</span><span class="sxs-lookup"><span data-stu-id="4a0ae-193">Calculation</span></span>                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| <span data-ttu-id="4a0ae-194">Acquisti nell'anno corrente</span><span class="sxs-lookup"><span data-stu-id="4a0ae-194">Purchase current year</span></span> | <span data-ttu-id="4a0ae-195">Acquisto nell'anno corrente = SUM('Righe fattura'\[Acquisti\])</span><span class="sxs-lookup"><span data-stu-id="4a0ae-195">Purchase current year = SUM('Invoice lines'\[Purchase\])</span></span>                                            |
| <span data-ttu-id="4a0ae-196">Acquisti nell'anno passato</span><span class="sxs-lookup"><span data-stu-id="4a0ae-196">Purchase last year</span></span>    | <span data-ttu-id="4a0ae-197">Acquisti nell'anno passato = CALCULATE(SUM('Righe fattura'\[Acquisti\]), SAMEPERIODLASTYEAR(Dates\[Data\]))</span><span class="sxs-lookup"><span data-stu-id="4a0ae-197">Purchase last year = CALCULATE(SUM('Invoice lines'\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\]))</span></span> |
| <span data-ttu-id="4a0ae-198">Crescita degli acquisti su base annua</span><span class="sxs-lookup"><span data-stu-id="4a0ae-198">YOY purchase growth</span></span>   | <span data-ttu-id="4a0ae-199">Crescita degli acquisti su base annua = \[Acquisti nell'anno corrente\] - \[Acquisti nell'anno passato\]</span><span class="sxs-lookup"><span data-stu-id="4a0ae-199">YOY purchase growth = \[Purchase current year\] – \[Purchase last year\]</span></span>                            |

<span data-ttu-id="4a0ae-200">Le seguenti dimensioni chiave nel contenuto vengono utilizzate come filtri per dividere le misure di aggregazione in modo da poter ottenere una maggiore granularità e fornire informazioni analitiche più approfondite.</span><span class="sxs-lookup"><span data-stu-id="4a0ae-200">The following key dimensions in the content are used as filters to slice the aggregate measurements, so that you can achieve more granularity and gain deeper analytical insights.</span></span>

| <span data-ttu-id="4a0ae-201">Entità</span><span class="sxs-lookup"><span data-stu-id="4a0ae-201">Entity</span></span>                 | <span data-ttu-id="4a0ae-202">Esempi di attributi</span><span class="sxs-lookup"><span data-stu-id="4a0ae-202">Examples of attributes</span></span>                                |
|------------------------|-------------------------------------------------------|
| <span data-ttu-id="4a0ae-203">Fornitori</span><span class="sxs-lookup"><span data-stu-id="4a0ae-203">Vendors</span></span>                | <span data-ttu-id="4a0ae-204">Gruppi di fornitori, paese o regioni del fornitore, nome del fornitore</span><span class="sxs-lookup"><span data-stu-id="4a0ae-204">Vendor groups, Vendor country or regions, Vendor name</span></span> |
| <span data-ttu-id="4a0ae-205">Prodotti</span><span class="sxs-lookup"><span data-stu-id="4a0ae-205">Products</span></span>               | <span data-ttu-id="4a0ae-206">Numero prodotto, nome prodotto, nome dei gruppi di articoli</span><span class="sxs-lookup"><span data-stu-id="4a0ae-206">Product number, Product name, Item groups name</span></span>        |
| <span data-ttu-id="4a0ae-207">Categorie di approvvigionamento</span><span class="sxs-lookup"><span data-stu-id="4a0ae-207">Procurement categories</span></span> | <span data-ttu-id="4a0ae-208">Categoria di approvvigionamento, nomi delle categorie di approvvigionamento</span><span class="sxs-lookup"><span data-stu-id="4a0ae-208">Procurement category, Procurement category names</span></span>      |
| <span data-ttu-id="4a0ae-209">Persone giuridiche</span><span class="sxs-lookup"><span data-stu-id="4a0ae-209">Legal entities</span></span>         | <span data-ttu-id="4a0ae-210">Nome persona giuridica</span><span class="sxs-lookup"><span data-stu-id="4a0ae-210">Legal entity name</span></span>                                     |
| <span data-ttu-id="4a0ae-211">Appuntamenti</span><span class="sxs-lookup"><span data-stu-id="4a0ae-211">Dates</span></span>                  | <span data-ttu-id="4a0ae-212">Date, offset anno</span><span class="sxs-lookup"><span data-stu-id="4a0ae-212">Dates, Year offset</span></span>                                    |

<span data-ttu-id="4a0ae-213">Per impostazione predefinita, il contenuto mostra i dati dell'anno di calendario corrente.</span><span class="sxs-lookup"><span data-stu-id="4a0ae-213">By default, the content shows data for the current calendar year.</span></span> <span data-ttu-id="4a0ae-214">Tuttavia, è possibile modificare il filtro della data nella sezione relativa ai filtri di report.</span><span class="sxs-lookup"><span data-stu-id="4a0ae-214">However, you can change the date filter in the report filters section.</span></span> <span data-ttu-id="4a0ae-215">È inoltre possibile modificare il filtro della società.</span><span class="sxs-lookup"><span data-stu-id="4a0ae-215">You can also change the company filter.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]