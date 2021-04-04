---
title: Contenuto Analisi delle spese di acquisto di Power BI
description: In questo argomento viene descritto cosa è incluso nel contenuto Analisi delle spese di acquisto di Power BI.
author: FrankDahl
manager: AnnBe
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
ms.openlocfilehash: a4149b13754b544558dbb5666fbec7df97e5c5d8
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559551"
---
# <a name="purchase-spend-analysis-power-bi-content"></a><span data-ttu-id="62020-103">Contenuto Analisi delle spese di acquisto di Power BI</span><span class="sxs-lookup"><span data-stu-id="62020-103">Purchase spend analysis Power BI content</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="62020-104">In questo argomento viene descritto cosa è incluso nel contenuto **Analisi delle spese di acquisto** di Microsoft Power BI.</span><span class="sxs-lookup"><span data-stu-id="62020-104">This topic describes what is included in the **Purchase spend analysis** Microsoft Power BI content.</span></span> <span data-ttu-id="62020-105">Descrive come accedere ai report di Power BI e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto.</span><span class="sxs-lookup"><span data-stu-id="62020-105">It explains how to access the Power BI reports, and provides information about the data model and entities that are used to build the content.</span></span>

## <a name="overview"></a><span data-ttu-id="62020-106">Panoramica</span><span class="sxs-lookup"><span data-stu-id="62020-106">Overview</span></span>

<span data-ttu-id="62020-107">Il contenuto di Power BI **Analisi delle spese di acquisto** è stato progettato per consentire ai responsabili acquisti e ai dirigenti responsabili di budget di tenere sotto controllo la spesa di acquisto.</span><span class="sxs-lookup"><span data-stu-id="62020-107">The **Purchase spend analysis** Power BI content was designed to help purchasing managers and managers who are responsible for budgets keep track of purchase spending.</span></span> <span data-ttu-id="62020-108">I responsabili possono analizzare la spesa d'acquisto nei seguenti modi:</span><span class="sxs-lookup"><span data-stu-id="62020-108">Managers can analyze purchase spending in the following ways:</span></span>

- <span data-ttu-id="62020-109">Acquisto da inizio anno (per gruppo di fornitori e singoli fornitori, per categoria di approvvigionamento e singoli prodotti e per ubicazione del fornitore)</span><span class="sxs-lookup"><span data-stu-id="62020-109">Year-to-date purchase (by vendor group and individual vendors, procurement category and individual products, and vendor location)</span></span>
- <span data-ttu-id="62020-110">Modifica di acquisto da inizio anno (per gruppo di fornitori e categoria di approvvigionamento)</span><span class="sxs-lookup"><span data-stu-id="62020-110">Year-over-year purchase change (by vendor group and procurement category)</span></span>

<span data-ttu-id="62020-111">Il contenuto utilizza dati transazionali di acquisto e offre sia una visualizzazione aggregata delle cifre di acquisto a livello di società che una scomposizione dettagliata della spesa di acquisto per fornitore e prodotto.</span><span class="sxs-lookup"><span data-stu-id="62020-111">The content uses purchase transactional data, and provides both an aggregate view of the company-wide purchase figures and a breakdown of purchase spending by vendor and product.</span></span> <span data-ttu-id="62020-112">I report evidenziano le modifiche nella spesa di acquisto nel tempo.</span><span class="sxs-lookup"><span data-stu-id="62020-112">Reports highlight changes in purchase spending over time.</span></span> <span data-ttu-id="62020-113">Di conseguenza, è possibile utilizzarli per avvisare i responsabili sulle tendenze positive e negative di spesa per singoli fornitori e prodotti.</span><span class="sxs-lookup"><span data-stu-id="62020-113">Therefore, the reports can be used to alert managers about positive and negative spending trends for individual vendors and products.</span></span> <span data-ttu-id="62020-114">Inoltre, i grafici mostrano la spesa di acquisto per categorie di approvvigionamento e gruppi di fornitori diversi.</span><span class="sxs-lookup"><span data-stu-id="62020-114">Additionally, charts show purchase spending for different procurement categories and vendor groups.</span></span> <span data-ttu-id="62020-115">Pertanto, i responsabili di categoria e regionali possono usare questi grafici per identificare i cambiamenti nel comportamento di spesa.</span><span class="sxs-lookup"><span data-stu-id="62020-115">Therefore, category and regional managers can use the charts to help identify changes in spending behavior.</span></span>

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="62020-116">Accesso al contenuto Power BI</span><span class="sxs-lookup"><span data-stu-id="62020-116">Accessing the Power BI content</span></span>
<span data-ttu-id="62020-117">Il contenuto di Power BI **Analisi delle spese di acquisto** viene mostrato nella pagina **Analisi di spesa e acquisto** (**Approvvigionamento** \> **Richieste di informazioni e report** \> **Analisi delle prestazioni di acquisto** \> **Analisi delle prestazioni di acquisto**).</span><span class="sxs-lookup"><span data-stu-id="62020-117">The **Purchase spend analysis** Power BI content is shown on the **Purchase and spend analysis** page (**Procurement and sourcing** \> **Inquiries and reports** \> **Purchase performance analysis** \> **Purchase and spend analysis**).</span></span>

## <a name="metrics-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="62020-118">Metriche incluse nel contenuto Power BI</span><span class="sxs-lookup"><span data-stu-id="62020-118">Metrics that are included in the Power BI content</span></span>
<span data-ttu-id="62020-119">Il contenuto di Power BI **Analisi delle spese di acquisto** include un report costituito da un set di metriche.</span><span class="sxs-lookup"><span data-stu-id="62020-119">The **Purchase spend analysis** Power BI content includes a report that consists of a set of metrics.</span></span> <span data-ttu-id="62020-120">Queste metriche vengono visualizzate come grafici, riquadri e tabelle.</span><span class="sxs-lookup"><span data-stu-id="62020-120">These metrics are visualized as charts, tiles, and tables.</span></span> 

<span data-ttu-id="62020-121">Nelle seguenti sezioni viene fornita una panoramica delle visualizzazioni.</span><span class="sxs-lookup"><span data-stu-id="62020-121">The following sections provide an overview of the visualizations.</span></span>

### <a name="purchase-by-vendor-report-page"></a><span data-ttu-id="62020-122">Pagina del report sugli acquisti per fornitore</span><span class="sxs-lookup"><span data-stu-id="62020-122">Purchase by vendor report page</span></span>
<span data-ttu-id="62020-123">**Grafici**</span><span class="sxs-lookup"><span data-stu-id="62020-123">**Charts**</span></span>
- <span data-ttu-id="62020-124">Primi 10 fornitori per acquisti (grafico a barre impilate)</span><span class="sxs-lookup"><span data-stu-id="62020-124">Top 10 vendors by purchase (stacked bar chart)</span></span>
- <span data-ttu-id="62020-125">Acquisti totali per gruppo di fornitori/paese/nome (grafico a torta)</span><span class="sxs-lookup"><span data-stu-id="62020-125">Total purchase by vendor group / country / name (pie chart)</span></span>
- <span data-ttu-id="62020-126">Acquisti per gruppo di fornitori/paese/nome (istogramma)</span><span class="sxs-lookup"><span data-stu-id="62020-126">Purchase by vendor group / country / name (column chart)</span></span>
- <span data-ttu-id="62020-127">Media degli acquisti per gruppo di fornitori/paese/nome (istogramma)</span><span class="sxs-lookup"><span data-stu-id="62020-127">Average purchase by vendor group / country / name (column chart)</span></span>

<span data-ttu-id="62020-128">**Riquadri**</span><span class="sxs-lookup"><span data-stu-id="62020-128">**Tiles**</span></span>
- <span data-ttu-id="62020-129">Totale acquisto</span><span class="sxs-lookup"><span data-stu-id="62020-129">Total purchase</span></span>
- <span data-ttu-id="62020-130">Crescita degli acquisti su base annua</span><span class="sxs-lookup"><span data-stu-id="62020-130">YOY purchase growth</span></span>
- <span data-ttu-id="62020-131">N. totale fornitori</span><span class="sxs-lookup"><span data-stu-id="62020-131">Total # vendors</span></span>
- <span data-ttu-id="62020-132">N. totale dei fornitori attivi</span><span class="sxs-lookup"><span data-stu-id="62020-132">Total # of active vendors</span></span>

<span data-ttu-id="62020-133">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="62020-133">**Example**</span></span>
<img src="media/spend1.png" alt="Purchase by vendor">

### <a name="purchase-by-product-report-page"></a><span data-ttu-id="62020-134">Pagina del report sugli acquisti per prodotto</span><span class="sxs-lookup"><span data-stu-id="62020-134">Purchase by product report page</span></span>

<span data-ttu-id="62020-135">**Grafici**</span><span class="sxs-lookup"><span data-stu-id="62020-135">**Charts**</span></span>
- <span data-ttu-id="62020-136">Acquisti per categoria di approvvigionamento/nome prodotto (istogramma)</span><span class="sxs-lookup"><span data-stu-id="62020-136">Purchase by procurement category / product name (column chart)</span></span>
- <span data-ttu-id="62020-137">Acquisti totali per categoria di approvvigionamento/nome prodotto (grafico a torta)</span><span class="sxs-lookup"><span data-stu-id="62020-137">Total purchase by procurement category / product name (pie chart)</span></span>
- <span data-ttu-id="62020-138">Primi 10 prodotti per acquisti (grafico a barre impilate)</span><span class="sxs-lookup"><span data-stu-id="62020-138">Top 10 products by purchase (stacked bar chart)</span></span>

<span data-ttu-id="62020-139">**Riquadri**</span><span class="sxs-lookup"><span data-stu-id="62020-139">**Tiles**</span></span>
- <span data-ttu-id="62020-140">N. totale di prodotti</span><span class="sxs-lookup"><span data-stu-id="62020-140">Total # of products</span></span></li>
- <span data-ttu-id="62020-141">Percentuale di prodotti attivi totali del numero totale di prodotti</span><span class="sxs-lookup"><span data-stu-id="62020-141">Total active products percentage of total # of products</span></span>
- <span data-ttu-id="62020-142">Numero di prodotti che rappresentano l'80% degli acquisti</span><span class="sxs-lookup"><span data-stu-id="62020-142">Number of products accounting for 80% purchase</span></span>

<span data-ttu-id="62020-143">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="62020-143">**Example**</span></span>


<img src="media/purchaseByProduct.png" alt="Purchase by Product">

### <a name="purchase-by-period-report-page"></a><span data-ttu-id="62020-144">Pagina del report sugli acquisti per periodo</span><span class="sxs-lookup"><span data-stu-id="62020-144">Purchase by period report page</span></span>
<span data-ttu-id="62020-145">Questa pagina nostra gli acquisti nell'anno corrente e nell'anno passato e crescita per categoria di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="62020-145">This page shows purchases this year and last year, and growth by procurement category.</span></span>

<span data-ttu-id="62020-146">**Grafici**</span><span class="sxs-lookup"><span data-stu-id="62020-146">**Charts**</span></span> 
- <span data-ttu-id="62020-147">Acquisti al mese/giorno (istogramma)</span><span class="sxs-lookup"><span data-stu-id="62020-147">Purchase by month / day (column chart)</span></span>
- <span data-ttu-id="62020-148">Scostamento di acquisti cumulativi su base annua (grafico a cascata)</span><span class="sxs-lookup"><span data-stu-id="62020-148">Cumulative purchase YOY variance (waterfall chart)</span></span>
- <span data-ttu-id="62020-149">Crescita degli acquisti totali su base annua (istogramma)</span><span class="sxs-lookup"><span data-stu-id="62020-149">Total purchase YOY growth (column chart)</span></span>
- <span data-ttu-id="62020-150">Rendiconto di approvvigionamento (matrice)</span><span class="sxs-lookup"><span data-stu-id="62020-150">Procurement statement (matrix)</span></span>

<span data-ttu-id="62020-151">**Riquadri**</span><span class="sxs-lookup"><span data-stu-id="62020-151">**Tiles**</span></span>
- <span data-ttu-id="62020-152">Crescita degli acquisti su base annua</span><span class="sxs-lookup"><span data-stu-id="62020-152">YOY purchase growth</span></span>
- <span data-ttu-id="62020-153">% di crescita degli acquisti su base annua</span><span class="sxs-lookup"><span data-stu-id="62020-153">YOY purchase growth %</span></span>

<span data-ttu-id="62020-154">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="62020-154">**Example**</span></span>
<img src="media/purchaseByPeriod.png" alt="Purchase by Period">

### <a name="purchase-by-vendor-location-report-page"></a><span data-ttu-id="62020-155">Pagina del report sugli acquisti per ubicazione del fornitore</span><span class="sxs-lookup"><span data-stu-id="62020-155">Purchase by vendor location report page</span></span>

<span data-ttu-id="62020-156">**Grafici**</span><span class="sxs-lookup"><span data-stu-id="62020-156">**Charts**</span></span>
- <span data-ttu-id="62020-157">Acquisti per città</span><span class="sxs-lookup"><span data-stu-id="62020-157">Purchase by city</span></span>
- <span data-ttu-id="62020-158">% di crescita su base annua degli acquisti</span><span class="sxs-lookup"><span data-stu-id="62020-158">Purchase YOY growth %</span></span>
- <span data-ttu-id="62020-159">Acquisti per paese</span><span class="sxs-lookup"><span data-stu-id="62020-159">Purchase by country</span></span>

<span data-ttu-id="62020-160">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="62020-160">**Example**</span></span>
<img src="media/purchByVendorLocation.png" alt="Purchase by Vendor Location">

### <a name="purchase-spend-analysis-by-time-report-page"></a><span data-ttu-id="62020-161">Pagina del report sull'analisi delle spese di acquisto in base all'ora</span><span class="sxs-lookup"><span data-stu-id="62020-161">Purchase spend analysis by time report page</span></span>

<span data-ttu-id="62020-162">**Grafici**</span><span class="sxs-lookup"><span data-stu-id="62020-162">**Charts**</span></span> 
- <span data-ttu-id="62020-163">Acquisti nell'anno corrente al mese/giorno (grafico a linee)</span><span class="sxs-lookup"><span data-stu-id="62020-163">Purchase current year by month / day (line chart)</span></span>
- <span data-ttu-id="62020-164">Acquisti nell'anno corrente e nell'anno passato (grafico a linee e colonne)</span><span class="sxs-lookup"><span data-stu-id="62020-164">Purchase current and last year (line and column chart)</span></span>

<span data-ttu-id="62020-165">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="62020-165">**Example**</span></span>
<img src="media/PurchByTIme.png" alt="Purchase by Time">

### <a name="purchase-spend-analysis-by-vendor-report-page"></a><span data-ttu-id="62020-166">Pagina del report sull'analisi delle spese di acquisto in base fornitore</span><span class="sxs-lookup"><span data-stu-id="62020-166">Purchase spend analysis by vendor report page</span></span>

<span data-ttu-id="62020-167">**Grafici**</span><span class="sxs-lookup"><span data-stu-id="62020-167">**Charts**</span></span> 
- <span data-ttu-id="62020-168">% di acquisti dei primi 10 fornitori (grafico a imbuto)</span><span class="sxs-lookup"><span data-stu-id="62020-168">Top 10 vendor purchase % of purchase (funnel)</span></span>
- <span data-ttu-id="62020-169">Primi 10 fornitori con aumento delle spese su base annua</span><span class="sxs-lookup"><span data-stu-id="62020-169">Top 10 vendors with increased spending YOY</span></span>
- <span data-ttu-id="62020-170">Primi 10 fornitori con diminuzione delle spese su base annua</span><span class="sxs-lookup"><span data-stu-id="62020-170">Top 10 vendors with decreased spending YOY</span></span>

<span data-ttu-id="62020-171">**Esempio** 
</span><span class="sxs-lookup"><span data-stu-id="62020-171">**Example** 
</span></span><img src="media/PurchSpendAnalysisByVendor.png" alt="Purchase spend by vendor">


## <a name="data-model-and-entities"></a><span data-ttu-id="62020-172">Modello dati ed entità</span><span class="sxs-lookup"><span data-stu-id="62020-172">Data model and entities</span></span>
<span data-ttu-id="62020-173">I seguenti dati vengono utilizzati per compilare le pagine di report nel contenuto Power BI **Analisi delle spese di acquisto**.</span><span class="sxs-lookup"><span data-stu-id="62020-173">The following data is used to fill the report pages in the **Purchase spend analysis** Power BI content.</span></span> <span data-ttu-id="62020-174">Questi dati vengono rappresentati come misure aggregate approntate nell'archivio entità.</span><span class="sxs-lookup"><span data-stu-id="62020-174">This data is represented as aggregate measurements that are staged in the Entity store.</span></span> <span data-ttu-id="62020-175">L'archivio entità è un database di Microsoft SQL Server che viene ottimizzato per l'analisi dei dati.</span><span class="sxs-lookup"><span data-stu-id="62020-175">The Entity store is a Microsoft SQL Server database that is optimized for analytics.</span></span> <span data-ttu-id="62020-176">Per ulteriori informazioni, vedere [Integrazione di Power BI con l'archivio entità](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="62020-176">For more information, see [Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span>

<span data-ttu-id="62020-177">Le misure di aggregazione in questo pacchetto di contenuti sono il sottoinsieme delle misure di aggregazione disponibili nel cubo Acquisiti in Microsoft Dynamics AX 2012 e Microsoft Dynamics AX 2012 R3.</span><span class="sxs-lookup"><span data-stu-id="62020-177">The aggregate measurements in this content are the subset of aggregate measurements that were available in the Purchase Cube in Microsoft Dynamics AX 2012 and Microsoft Dynamics AX 2012 R3.</span></span> <span data-ttu-id="62020-178">Per rappresentare le misure di aggregazione del cubo nell'Archivio entità, è necessario renderle distribuibili.</span><span class="sxs-lookup"><span data-stu-id="62020-178">To stage the cube's aggregate measurements in the Entity store, you must make them deployable.</span></span> <span data-ttu-id="62020-179">Per ulteriori informazioni, vedere la procedura per la rappresentazione delle misure di aggregazione nell'Archivio entità in [Integrazione di Power BI con l'archivio entità](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="62020-179">For more information, see the procedure for staging aggregate measurements in the Entity store in [Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span> <span data-ttu-id="62020-180">Le seguenti misure di aggregazione chiave sono disponibili direttamente dall'entità delle righe della fattura e sono utilizzate come base del contenuto.</span><span class="sxs-lookup"><span data-stu-id="62020-180">The following key aggregate measurements are available directly from the Invoice lines entity and are used as the basis of the content.</span></span>

| <span data-ttu-id="62020-181">Entità</span><span class="sxs-lookup"><span data-stu-id="62020-181">Entity</span></span>        | <span data-ttu-id="62020-182">Misure di aggregazione chiave</span><span class="sxs-lookup"><span data-stu-id="62020-182">Key aggregate measurements</span></span> | <span data-ttu-id="62020-183">Origine dati</span><span class="sxs-lookup"><span data-stu-id="62020-183">Data source</span></span>                                 | <span data-ttu-id="62020-184">Campo</span><span class="sxs-lookup"><span data-stu-id="62020-184">Field</span></span>              | <span data-ttu-id="62020-185">Descrizione</span><span class="sxs-lookup"><span data-stu-id="62020-185">Description</span></span>                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| <span data-ttu-id="62020-186">Righe fattura</span><span class="sxs-lookup"><span data-stu-id="62020-186">Invoice lines</span></span> | <span data-ttu-id="62020-187">Acquisti</span><span class="sxs-lookup"><span data-stu-id="62020-187">Purchase</span></span>                   | <span data-ttu-id="62020-188">VendInvoiceTrans</span><span class="sxs-lookup"><span data-stu-id="62020-188">VendInvoiceTrans</span></span>                            | <span data-ttu-id="62020-189">SUM(LineAmountMST)</span><span class="sxs-lookup"><span data-stu-id="62020-189">SUM(LineAmountMST)</span></span> | <span data-ttu-id="62020-190">Importo nella valuta di contabilizzazione.</span><span class="sxs-lookup"><span data-stu-id="62020-190">The amount in the accounting currency.</span></span> |

<span data-ttu-id="62020-191">Nella seguente tabella vengono illustrate le misurazioni chiave nel contenuto calcolate dall'entità delle righe della fattura.</span><span class="sxs-lookup"><span data-stu-id="62020-191">The following table shows the key measurements in the content that are calculated from the Invoice lines entity.</span></span>

| <span data-ttu-id="62020-192">Unità di misura</span><span class="sxs-lookup"><span data-stu-id="62020-192">Measure</span></span>               | <span data-ttu-id="62020-193">Calcolo</span><span class="sxs-lookup"><span data-stu-id="62020-193">Calculation</span></span>                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| <span data-ttu-id="62020-194">Acquisti nell'anno corrente</span><span class="sxs-lookup"><span data-stu-id="62020-194">Purchase current year</span></span> | <span data-ttu-id="62020-195">Acquisto nell'anno corrente = SUM('Righe fattura'\[Acquisti\])</span><span class="sxs-lookup"><span data-stu-id="62020-195">Purchase current year = SUM('Invoice lines'\[Purchase\])</span></span>                                            |
| <span data-ttu-id="62020-196">Acquisti nell'anno passato</span><span class="sxs-lookup"><span data-stu-id="62020-196">Purchase last year</span></span>    | <span data-ttu-id="62020-197">Acquisti nell'anno passato = CALCULATE(SUM('Righe fattura'\[Acquisti\]), SAMEPERIODLASTYEAR(Dates\[Data\]))</span><span class="sxs-lookup"><span data-stu-id="62020-197">Purchase last year = CALCULATE(SUM('Invoice lines'\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\]))</span></span> |
| <span data-ttu-id="62020-198">Crescita degli acquisti su base annua</span><span class="sxs-lookup"><span data-stu-id="62020-198">YOY purchase growth</span></span>   | <span data-ttu-id="62020-199">Crescita degli acquisti su base annua = \[Acquisti nell'anno corrente\] - \[Acquisti nell'anno passato\]</span><span class="sxs-lookup"><span data-stu-id="62020-199">YOY purchase growth = \[Purchase current year\] – \[Purchase last year\]</span></span>                            |

<span data-ttu-id="62020-200">Le seguenti dimensioni chiave nel contenuto vengono utilizzate come filtri per dividere le misure di aggregazione in modo da poter ottenere una maggiore granularità e fornire informazioni analitiche più approfondite.</span><span class="sxs-lookup"><span data-stu-id="62020-200">The following key dimensions in the content are used as filters to slice the aggregate measurements, so that you can achieve more granularity and gain deeper analytical insights.</span></span>

| <span data-ttu-id="62020-201">Entità</span><span class="sxs-lookup"><span data-stu-id="62020-201">Entity</span></span>                 | <span data-ttu-id="62020-202">Esempi di attributi</span><span class="sxs-lookup"><span data-stu-id="62020-202">Examples of attributes</span></span>                                |
|------------------------|-------------------------------------------------------|
| <span data-ttu-id="62020-203">Fornitori</span><span class="sxs-lookup"><span data-stu-id="62020-203">Vendors</span></span>                | <span data-ttu-id="62020-204">Gruppi di fornitori, paese o regioni del fornitore, nome del fornitore</span><span class="sxs-lookup"><span data-stu-id="62020-204">Vendor groups, Vendor country or regions, Vendor name</span></span> |
| <span data-ttu-id="62020-205">Prodotti</span><span class="sxs-lookup"><span data-stu-id="62020-205">Products</span></span>               | <span data-ttu-id="62020-206">Numero prodotto, nome prodotto, nome dei gruppi di articoli</span><span class="sxs-lookup"><span data-stu-id="62020-206">Product number, Product name, Item groups name</span></span>        |
| <span data-ttu-id="62020-207">Categorie di approvvigionamento</span><span class="sxs-lookup"><span data-stu-id="62020-207">Procurement categories</span></span> | <span data-ttu-id="62020-208">Categoria di approvvigionamento, nomi delle categorie di approvvigionamento</span><span class="sxs-lookup"><span data-stu-id="62020-208">Procurement category, Procurement category names</span></span>      |
| <span data-ttu-id="62020-209">Persone giuridiche</span><span class="sxs-lookup"><span data-stu-id="62020-209">Legal entities</span></span>         | <span data-ttu-id="62020-210">Nome persona giuridica</span><span class="sxs-lookup"><span data-stu-id="62020-210">Legal entity name</span></span>                                     |
| <span data-ttu-id="62020-211">Appuntamenti</span><span class="sxs-lookup"><span data-stu-id="62020-211">Dates</span></span>                  | <span data-ttu-id="62020-212">Date, offset anno</span><span class="sxs-lookup"><span data-stu-id="62020-212">Dates, Year offset</span></span>                                    |

<span data-ttu-id="62020-213">Per impostazione predefinita, il contenuto mostra i dati dell'anno di calendario corrente.</span><span class="sxs-lookup"><span data-stu-id="62020-213">By default, the content shows data for the current calendar year.</span></span> <span data-ttu-id="62020-214">Tuttavia, è possibile modificare il filtro della data nella sezione relativa ai filtri di report.</span><span class="sxs-lookup"><span data-stu-id="62020-214">However, you can change the date filter in the report filters section.</span></span> <span data-ttu-id="62020-215">È inoltre possibile modificare il filtro della società.</span><span class="sxs-lookup"><span data-stu-id="62020-215">You can also change the company filter.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]