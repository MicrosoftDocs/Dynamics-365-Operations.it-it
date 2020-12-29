---
title: Contenuto Power BI sull'analisi delle spese di acquisto
description: In questo argomento viene descritto cosa è incluso nel contenuto di Power BI per l'analisi delle spese di acquisto. Viene descritto come accedere ai report inclusi nel contenuto e vengono fornite informazioni sul modello dati e sulle entità utilizzati per creare il contenuto.
author: FrankDahl
manager: AnnBe
ms.date: 04/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 3f556cf2e506c57e465c2a86485d2cdd4cf8b65e
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680616"
---
# <a name="purchase-spend-analysis-power-bi-content"></a><span data-ttu-id="c2ff9-104">Contenuto Power BI sull'analisi delle spese di acquisto</span><span class="sxs-lookup"><span data-stu-id="c2ff9-104">Purchase spend analysis Power BI content</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c2ff9-105">In questo argomento viene descritto cosa è incluso nel contenuto di Power BI **Analisi delle spese di acquisto**.</span><span class="sxs-lookup"><span data-stu-id="c2ff9-105">This topic describes what is included in the **Purchase spend analysis** Microsoft Power BI content.</span></span> <span data-ttu-id="c2ff9-106">Descrive come accedere ai report di Power BI e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto.</span><span class="sxs-lookup"><span data-stu-id="c2ff9-106">It explains how to access the Power BI reports, and provides information about the data model and entities that are used to build the content.</span></span>

## <a name="overview"></a><span data-ttu-id="c2ff9-107">Panoramica</span><span class="sxs-lookup"><span data-stu-id="c2ff9-107">Overview</span></span>

<span data-ttu-id="c2ff9-108">Il contenuto di Power BI **Analisi delle spese di acquisto** è stato progettato per consentire ai responsabili acquisti e ai dirigenti responsabili di budget di tenere sotto controllo la spesa di acquisto.</span><span class="sxs-lookup"><span data-stu-id="c2ff9-108">The **Purchase spend analysis** Power BI content was designed to help purchasing managers and managers who are responsible for budgets keep track of purchase spending.</span></span> <span data-ttu-id="c2ff9-109">I responsabili possono analizzare la spesa d'acquisto nei seguenti modi:</span><span class="sxs-lookup"><span data-stu-id="c2ff9-109">Managers can analyze purchase spending in the following ways:</span></span>

- <span data-ttu-id="c2ff9-110">Acquisto da inizio anno (per gruppo di fornitori e singoli fornitori, per categoria di approvvigionamento e singoli prodotti e per ubicazione del fornitore)</span><span class="sxs-lookup"><span data-stu-id="c2ff9-110">Year-to-date purchase (by vendor group and individual vendors, procurement category and individual products, and vendor location)</span></span>
- <span data-ttu-id="c2ff9-111">Modifica di acquisto da inizio anno (per gruppo di fornitori e categoria di approvvigionamento)</span><span class="sxs-lookup"><span data-stu-id="c2ff9-111">Year-over-year purchase change (by vendor group and procurement category)</span></span>

<span data-ttu-id="c2ff9-112">Il contenuto utilizza dati transazionali di acquisto e offre sia una visualizzazione aggregata delle cifre di acquisto a livello di società che una scomposizione dettagliata della spesa di acquisto per fornitore e prodotto.</span><span class="sxs-lookup"><span data-stu-id="c2ff9-112">The content uses purchase transactional data, and provides both an aggregate view of the company-wide purchase figures and a breakdown of purchase spending by vendor and product.</span></span> <span data-ttu-id="c2ff9-113">I report evidenziano le modifiche nella spesa di acquisto nel tempo.</span><span class="sxs-lookup"><span data-stu-id="c2ff9-113">Reports highlight changes in purchase spending over time.</span></span> <span data-ttu-id="c2ff9-114">Di conseguenza, è possibile utilizzarli per avvisare i responsabili sulle tendenze positive e negative di spesa per singoli fornitori e prodotti.</span><span class="sxs-lookup"><span data-stu-id="c2ff9-114">Therefore, the reports can be used to alert managers about positive and negative spending trends for individual vendors and products.</span></span> <span data-ttu-id="c2ff9-115">Inoltre, i grafici mostrano la spesa di acquisto per categorie di approvvigionamento e gruppi di fornitori diversi.</span><span class="sxs-lookup"><span data-stu-id="c2ff9-115">Additionally, charts show purchase spending for different procurement categories and vendor groups.</span></span> <span data-ttu-id="c2ff9-116">Pertanto, i responsabili di categoria e regionali possono usare questi grafici per identificare i cambiamenti nel comportamento di spesa.</span><span class="sxs-lookup"><span data-stu-id="c2ff9-116">Therefore, category and regional managers can use the charts to help identify changes in spending behavior.</span></span>

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="c2ff9-117">Accesso al contenuto Power BI</span><span class="sxs-lookup"><span data-stu-id="c2ff9-117">Accessing the Power BI content</span></span>
<span data-ttu-id="c2ff9-118">Il contenuto di Power BI **Analisi delle spese di acquisto** viene mostrato nella pagina **Analisi di spesa e acquisto** (**Approvvigionamento** \> **Richieste di informazioni e report** \> **Analisi delle prestazioni di acquisto** \> **Analisi delle prestazioni di acquisto**).</span><span class="sxs-lookup"><span data-stu-id="c2ff9-118">The **Purchase spend analysis** Power BI content is shown on the **Purchase and spend analysis** page (**Procurement and sourcing** \> **Inquiries and reports** \> **Purchase performance analysis** \> **Purchase and spend analysis**).</span></span>

## <a name="metrics-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="c2ff9-119">Metriche incluse nel contenuto Power BI</span><span class="sxs-lookup"><span data-stu-id="c2ff9-119">Metrics that are included in the Power BI content</span></span>
<span data-ttu-id="c2ff9-120">Il contenuto di Power BI **Analisi delle spese di acquisto** include un report costituito da un set di metriche.</span><span class="sxs-lookup"><span data-stu-id="c2ff9-120">The **Purchase spend analysis** Power BI content includes a report that consists of a set of metrics.</span></span> <span data-ttu-id="c2ff9-121">Queste metriche vengono visualizzate come grafici, riquadri e tabelle.</span><span class="sxs-lookup"><span data-stu-id="c2ff9-121">These metrics are visualized as charts, tiles, and tables.</span></span> 

<span data-ttu-id="c2ff9-122">Nelle seguenti sezioni viene fornita una panoramica delle visualizzazioni.</span><span class="sxs-lookup"><span data-stu-id="c2ff9-122">The following sections provide an overview of the visualizations.</span></span>

### <a name="purchase-by-vendor-report-page"></a><span data-ttu-id="c2ff9-123">Pagina del report sugli acquisti per fornitore</span><span class="sxs-lookup"><span data-stu-id="c2ff9-123">Purchase by vendor report page</span></span>
<span data-ttu-id="c2ff9-124">**Grafici**</span><span class="sxs-lookup"><span data-stu-id="c2ff9-124">**Charts**</span></span>
- <span data-ttu-id="c2ff9-125">Primi 10 fornitori per acquisti (grafico a barre impilate)</span><span class="sxs-lookup"><span data-stu-id="c2ff9-125">Top 10 vendors by purchase (stacked bar chart)</span></span>
- <span data-ttu-id="c2ff9-126">Acquisti totali per gruppo di fornitori/paese/nome (grafico a torta)</span><span class="sxs-lookup"><span data-stu-id="c2ff9-126">Total purchase by vendor group / country / name (pie chart)</span></span>
- <span data-ttu-id="c2ff9-127">Acquisti per gruppo di fornitori/paese/nome (istogramma)</span><span class="sxs-lookup"><span data-stu-id="c2ff9-127">Purchase by vendor group / country / name (column chart)</span></span>
- <span data-ttu-id="c2ff9-128">Media degli acquisti per gruppo di fornitori/paese/nome (istogramma)</span><span class="sxs-lookup"><span data-stu-id="c2ff9-128">Average purchase by vendor group / country / name (column chart)</span></span>

<span data-ttu-id="c2ff9-129">**Riquadri**</span><span class="sxs-lookup"><span data-stu-id="c2ff9-129">**Tiles**</span></span>
- <span data-ttu-id="c2ff9-130">Totale acquisto</span><span class="sxs-lookup"><span data-stu-id="c2ff9-130">Total purchase</span></span>
- <span data-ttu-id="c2ff9-131">Crescita degli acquisti su base annua</span><span class="sxs-lookup"><span data-stu-id="c2ff9-131">YOY purchase growth</span></span>
- <span data-ttu-id="c2ff9-132">N. totale fornitori</span><span class="sxs-lookup"><span data-stu-id="c2ff9-132">Total # vendors</span></span>
- <span data-ttu-id="c2ff9-133">N. totale dei fornitori attivi</span><span class="sxs-lookup"><span data-stu-id="c2ff9-133">Total # of active vendors</span></span>

<span data-ttu-id="c2ff9-134">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="c2ff9-134">**Example**</span></span>
<img src="media/spend1.png" alt="Purchase by vendor">

### <a name="purchase-by-product-report-page"></a><span data-ttu-id="c2ff9-135">Pagina del report sugli acquisti per prodotto</span><span class="sxs-lookup"><span data-stu-id="c2ff9-135">Purchase by product report page</span></span>

<span data-ttu-id="c2ff9-136">**Grafici**</span><span class="sxs-lookup"><span data-stu-id="c2ff9-136">**Charts**</span></span>
- <span data-ttu-id="c2ff9-137">Acquisti per categoria di approvvigionamento/nome prodotto (istogramma)</span><span class="sxs-lookup"><span data-stu-id="c2ff9-137">Purchase by procurement category / product name (column chart)</span></span>
- <span data-ttu-id="c2ff9-138">Acquisti totali per categoria di approvvigionamento/nome prodotto (grafico a torta)</span><span class="sxs-lookup"><span data-stu-id="c2ff9-138">Total purchase by procurement category / product name (pie chart)</span></span>
- <span data-ttu-id="c2ff9-139">Primi 10 prodotti per acquisti (grafico a barre impilate)</span><span class="sxs-lookup"><span data-stu-id="c2ff9-139">Top 10 products by purchase (stacked bar chart)</span></span>

<span data-ttu-id="c2ff9-140">**Riquadri**</span><span class="sxs-lookup"><span data-stu-id="c2ff9-140">**Tiles**</span></span>
- <span data-ttu-id="c2ff9-141">N. totale di prodotti</span><span class="sxs-lookup"><span data-stu-id="c2ff9-141">Total # of products</span></span></li>
- <span data-ttu-id="c2ff9-142">Percentuale di prodotti attivi totali del numero totale di prodotti</span><span class="sxs-lookup"><span data-stu-id="c2ff9-142">Total active products percentage of total # of products</span></span>
- <span data-ttu-id="c2ff9-143">Numero di prodotti che rappresentano l'80% degli acquisti</span><span class="sxs-lookup"><span data-stu-id="c2ff9-143">Number of products accounting for 80% purchase</span></span>

<span data-ttu-id="c2ff9-144">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="c2ff9-144">**Example**</span></span>


<img src="media/purchaseByProduct.png" alt="Purchase by Product">

### <a name="purchase-by-period-report-page"></a><span data-ttu-id="c2ff9-145">Pagina del report sugli acquisti per periodo</span><span class="sxs-lookup"><span data-stu-id="c2ff9-145">Purchase by period report page</span></span>
<span data-ttu-id="c2ff9-146">Questa pagina nostra gli acquisti nell'anno corrente e nell'anno passato e crescita per categoria di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="c2ff9-146">This page shows purchases this year and last year, and growth by procurement category.</span></span>

<span data-ttu-id="c2ff9-147">**Grafici**</span><span class="sxs-lookup"><span data-stu-id="c2ff9-147">**Charts**</span></span> 
- <span data-ttu-id="c2ff9-148">Acquisti al mese/giorno (istogramma)</span><span class="sxs-lookup"><span data-stu-id="c2ff9-148">Purchase by month / day (column chart)</span></span>
- <span data-ttu-id="c2ff9-149">Scostamento di acquisti cumulativi su base annua (grafico a cascata)</span><span class="sxs-lookup"><span data-stu-id="c2ff9-149">Cumulative purchase YOY variance (waterfall chart)</span></span>
- <span data-ttu-id="c2ff9-150">Crescita degli acquisti totali su base annua (istogramma)</span><span class="sxs-lookup"><span data-stu-id="c2ff9-150">Total purchase YOY growth (column chart)</span></span>
- <span data-ttu-id="c2ff9-151">Rendiconto di approvvigionamento (matrice)</span><span class="sxs-lookup"><span data-stu-id="c2ff9-151">Procurement statement (matrix)</span></span>

<span data-ttu-id="c2ff9-152">**Riquadri**</span><span class="sxs-lookup"><span data-stu-id="c2ff9-152">**Tiles**</span></span>
- <span data-ttu-id="c2ff9-153">Crescita degli acquisti su base annua</span><span class="sxs-lookup"><span data-stu-id="c2ff9-153">YOY purchase growth</span></span>
- <span data-ttu-id="c2ff9-154">% di crescita degli acquisti su base annua</span><span class="sxs-lookup"><span data-stu-id="c2ff9-154">YOY purchase growth %</span></span>

<span data-ttu-id="c2ff9-155">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="c2ff9-155">**Example**</span></span>
<img src="media/purchaseByPeriod.png" alt="Purchase by Period">

### <a name="purchase-by-vendor-location-report-page"></a><span data-ttu-id="c2ff9-156">Pagina del report sugli acquisti per ubicazione del fornitore</span><span class="sxs-lookup"><span data-stu-id="c2ff9-156">Purchase by vendor location report page</span></span>

<span data-ttu-id="c2ff9-157">**Grafici**</span><span class="sxs-lookup"><span data-stu-id="c2ff9-157">**Charts**</span></span>
- <span data-ttu-id="c2ff9-158">Acquisti per città</span><span class="sxs-lookup"><span data-stu-id="c2ff9-158">Purchase by city</span></span>
- <span data-ttu-id="c2ff9-159">% di crescita su base annua degli acquisti</span><span class="sxs-lookup"><span data-stu-id="c2ff9-159">Purchase YOY growth %</span></span>
- <span data-ttu-id="c2ff9-160">Acquisti per paese</span><span class="sxs-lookup"><span data-stu-id="c2ff9-160">Purchase by country</span></span>

<span data-ttu-id="c2ff9-161">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="c2ff9-161">**Example**</span></span>
<img src="media/purchByVendorLocation.png" alt="Purchase by Vendor Location">

### <a name="purchase-spend-analysis-by-time-report-page"></a><span data-ttu-id="c2ff9-162">Pagina del report sull'analisi delle spese di acquisto in base all'ora</span><span class="sxs-lookup"><span data-stu-id="c2ff9-162">Purchase spend analysis by time report page</span></span>

<span data-ttu-id="c2ff9-163">**Grafici**</span><span class="sxs-lookup"><span data-stu-id="c2ff9-163">**Charts**</span></span> 
- <span data-ttu-id="c2ff9-164">Acquisti nell'anno corrente al mese/giorno (grafico a linee)</span><span class="sxs-lookup"><span data-stu-id="c2ff9-164">Purchase current year by month / day (line chart)</span></span>
- <span data-ttu-id="c2ff9-165">Acquisti nell'anno corrente e nell'anno passato (grafico a linee e colonne)</span><span class="sxs-lookup"><span data-stu-id="c2ff9-165">Purchase current and last year (line and column chart)</span></span>

<span data-ttu-id="c2ff9-166">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="c2ff9-166">**Example**</span></span>
<img src="media/PurchByTIme.png" alt="Purchase by Time">

### <a name="purchase-spend-analysis-by-vendor-report-page"></a><span data-ttu-id="c2ff9-167">Pagina del report sull'analisi delle spese di acquisto in base fornitore</span><span class="sxs-lookup"><span data-stu-id="c2ff9-167">Purchase spend analysis by vendor report page</span></span>

<span data-ttu-id="c2ff9-168">**Grafici**</span><span class="sxs-lookup"><span data-stu-id="c2ff9-168">**Charts**</span></span> 
- <span data-ttu-id="c2ff9-169">% di acquisti dei primi 10 fornitori (grafico a imbuto)</span><span class="sxs-lookup"><span data-stu-id="c2ff9-169">Top 10 vendor purchase % of purchase (funnel)</span></span>
- <span data-ttu-id="c2ff9-170">Primi 10 fornitori con aumento delle spese su base annua</span><span class="sxs-lookup"><span data-stu-id="c2ff9-170">Top 10 vendors with increased spending YOY</span></span>
- <span data-ttu-id="c2ff9-171">Primi 10 fornitori con diminuzione delle spese su base annua</span><span class="sxs-lookup"><span data-stu-id="c2ff9-171">Top 10 vendors with decreased spending YOY</span></span>

<span data-ttu-id="c2ff9-172">**Esempio** 
</span><span class="sxs-lookup"><span data-stu-id="c2ff9-172">**Example** 
</span></span><img src="media/PurchSpendAnalysisByVendor.png" alt="Purchase spend by vendor">


## <a name="data-model-and-entities"></a><span data-ttu-id="c2ff9-173">Modello dati ed entità</span><span class="sxs-lookup"><span data-stu-id="c2ff9-173">Data model and entities</span></span>
<span data-ttu-id="c2ff9-174">I seguenti dati vengono utilizzati per compilare le pagine di report nel contenuto Power BI **Analisi delle spese di acquisto**.</span><span class="sxs-lookup"><span data-stu-id="c2ff9-174">The following data is used to fill the report pages in the **Purchase spend analysis** Power BI content.</span></span> <span data-ttu-id="c2ff9-175">Questi dati vengono rappresentati come misure aggregate approntate nell'archivio entità.</span><span class="sxs-lookup"><span data-stu-id="c2ff9-175">This data is represented as aggregate measurements that are staged in the Entity store.</span></span> <span data-ttu-id="c2ff9-176">L'archivio entità è un database di Microsoft SQL Server che viene ottimizzato per l'analisi dei dati.</span><span class="sxs-lookup"><span data-stu-id="c2ff9-176">The Entity store is a Microsoft SQL Server database that is optimized for analytics.</span></span> <span data-ttu-id="c2ff9-177">Per ulteriori informazioni, vedere [Integrazione di Power BI con l'archivio entità](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="c2ff9-177">For more information, see [Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span>

<span data-ttu-id="c2ff9-178">Le misure di aggregazione in questo pacchetto di contenuti sono il sottoinsieme delle misure di aggregazione disponibili nel cubo Acquisiti in Microsoft Dynamics AX 2012 e Microsoft Dynamics AX 2012 R3.</span><span class="sxs-lookup"><span data-stu-id="c2ff9-178">The aggregate measurements in this content are the subset of aggregate measurements that were available in the Purchase Cube in Microsoft Dynamics AX 2012 and Microsoft Dynamics AX 2012 R3.</span></span> <span data-ttu-id="c2ff9-179">Per rappresentare le misure di aggregazione del cubo nell'Archivio entità, è necessario renderle distribuibili.</span><span class="sxs-lookup"><span data-stu-id="c2ff9-179">To stage the cube's aggregate measurements in the Entity store, you must make them deployable.</span></span> <span data-ttu-id="c2ff9-180">Per ulteriori informazioni, vedere la procedura per la rappresentazione delle misure di aggregazione nell'Archivio entità in [Integrazione di Power BI con l'archivio entità](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="c2ff9-180">For more information, see the procedure for staging aggregate measurements in the Entity store in [Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span> <span data-ttu-id="c2ff9-181">Le seguenti misure di aggregazione chiave sono disponibili direttamente dall'entità delle righe della fattura e sono utilizzate come base del contenuto.</span><span class="sxs-lookup"><span data-stu-id="c2ff9-181">The following key aggregate measurements are available directly from the Invoice lines entity and are used as the basis of the content.</span></span>

| <span data-ttu-id="c2ff9-182">Entità</span><span class="sxs-lookup"><span data-stu-id="c2ff9-182">Entity</span></span>        | <span data-ttu-id="c2ff9-183">Misure di aggregazione chiave</span><span class="sxs-lookup"><span data-stu-id="c2ff9-183">Key aggregate measurements</span></span> | <span data-ttu-id="c2ff9-184">Origine dati</span><span class="sxs-lookup"><span data-stu-id="c2ff9-184">Data source</span></span>                                 | <span data-ttu-id="c2ff9-185">Campo</span><span class="sxs-lookup"><span data-stu-id="c2ff9-185">Field</span></span>              | <span data-ttu-id="c2ff9-186">descrizione</span><span class="sxs-lookup"><span data-stu-id="c2ff9-186">Description</span></span>                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| <span data-ttu-id="c2ff9-187">Righe fattura</span><span class="sxs-lookup"><span data-stu-id="c2ff9-187">Invoice lines</span></span> | <span data-ttu-id="c2ff9-188">Acquisti</span><span class="sxs-lookup"><span data-stu-id="c2ff9-188">Purchase</span></span>                   | <span data-ttu-id="c2ff9-189">VendInvoiceTrans</span><span class="sxs-lookup"><span data-stu-id="c2ff9-189">VendInvoiceTrans</span></span>                            | <span data-ttu-id="c2ff9-190">SUM(LineAmountMST)</span><span class="sxs-lookup"><span data-stu-id="c2ff9-190">SUM(LineAmountMST)</span></span> | <span data-ttu-id="c2ff9-191">Importo nella valuta di contabilizzazione.</span><span class="sxs-lookup"><span data-stu-id="c2ff9-191">The amount in the accounting currency.</span></span> |

<span data-ttu-id="c2ff9-192">Nella seguente tabella vengono illustrate le misurazioni chiave nel contenuto calcolate dall'entità delle righe della fattura.</span><span class="sxs-lookup"><span data-stu-id="c2ff9-192">The following table shows the key measurements in the content that are calculated from the Invoice lines entity.</span></span>

| <span data-ttu-id="c2ff9-193">Unità di misura</span><span class="sxs-lookup"><span data-stu-id="c2ff9-193">Measure</span></span>               | <span data-ttu-id="c2ff9-194">Calcolo</span><span class="sxs-lookup"><span data-stu-id="c2ff9-194">Calculation</span></span>                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| <span data-ttu-id="c2ff9-195">Acquisti nell'anno corrente</span><span class="sxs-lookup"><span data-stu-id="c2ff9-195">Purchase current year</span></span> | <span data-ttu-id="c2ff9-196">Acquisto nell'anno corrente = SUM('Righe fattura'\[Acquisti\])</span><span class="sxs-lookup"><span data-stu-id="c2ff9-196">Purchase current year = SUM('Invoice lines'\[Purchase\])</span></span>                                            |
| <span data-ttu-id="c2ff9-197">Acquisti nell'anno passato</span><span class="sxs-lookup"><span data-stu-id="c2ff9-197">Purchase last year</span></span>    | <span data-ttu-id="c2ff9-198">Acquisti nell'anno passato = CALCULATE(SUM('Righe fattura'\[Acquisti\]), SAMEPERIODLASTYEAR(Dates\[Data\]))</span><span class="sxs-lookup"><span data-stu-id="c2ff9-198">Purchase last year = CALCULATE(SUM('Invoice lines'\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\]))</span></span> |
| <span data-ttu-id="c2ff9-199">Crescita degli acquisti su base annua</span><span class="sxs-lookup"><span data-stu-id="c2ff9-199">YOY purchase growth</span></span>   | <span data-ttu-id="c2ff9-200">Crescita degli acquisti su base annua = \[Acquisti nell'anno corrente\] - \[Acquisti nell'anno passato\]</span><span class="sxs-lookup"><span data-stu-id="c2ff9-200">YOY purchase growth = \[Purchase current year\] – \[Purchase last year\]</span></span>                            |

<span data-ttu-id="c2ff9-201">Le seguenti dimensioni chiave nel contenuto vengono utilizzate come filtri per dividere le misure di aggregazione in modo da poter ottenere una maggiore granularità e fornire informazioni analitiche più approfondite.</span><span class="sxs-lookup"><span data-stu-id="c2ff9-201">The following key dimensions in the content are used as filters to slice the aggregate measurements, so that you can achieve more granularity and gain deeper analytical insights.</span></span>

| <span data-ttu-id="c2ff9-202">Entità</span><span class="sxs-lookup"><span data-stu-id="c2ff9-202">Entity</span></span>                 | <span data-ttu-id="c2ff9-203">Esempi di attributi</span><span class="sxs-lookup"><span data-stu-id="c2ff9-203">Examples of attributes</span></span>                                |
|------------------------|-------------------------------------------------------|
| <span data-ttu-id="c2ff9-204">Fornitori</span><span class="sxs-lookup"><span data-stu-id="c2ff9-204">Vendors</span></span>                | <span data-ttu-id="c2ff9-205">Gruppi di fornitori, paese o regioni del fornitore, nome del fornitore</span><span class="sxs-lookup"><span data-stu-id="c2ff9-205">Vendor groups, Vendor country or regions, Vendor name</span></span> |
| <span data-ttu-id="c2ff9-206">Prodotti</span><span class="sxs-lookup"><span data-stu-id="c2ff9-206">Products</span></span>               | <span data-ttu-id="c2ff9-207">Numero prodotto, nome prodotto, nome dei gruppi di articoli</span><span class="sxs-lookup"><span data-stu-id="c2ff9-207">Product number, Product name, Item groups name</span></span>        |
| <span data-ttu-id="c2ff9-208">Categorie di approvvigionamento</span><span class="sxs-lookup"><span data-stu-id="c2ff9-208">Procurement categories</span></span> | <span data-ttu-id="c2ff9-209">Categoria di approvvigionamento, nomi delle categorie di approvvigionamento</span><span class="sxs-lookup"><span data-stu-id="c2ff9-209">Procurement category, Procurement category names</span></span>      |
| <span data-ttu-id="c2ff9-210">Persone giuridiche</span><span class="sxs-lookup"><span data-stu-id="c2ff9-210">Legal entities</span></span>         | <span data-ttu-id="c2ff9-211">Nome persona giuridica</span><span class="sxs-lookup"><span data-stu-id="c2ff9-211">Legal entity name</span></span>                                     |
| <span data-ttu-id="c2ff9-212">Appuntamenti</span><span class="sxs-lookup"><span data-stu-id="c2ff9-212">Dates</span></span>                  | <span data-ttu-id="c2ff9-213">Date, offset anno</span><span class="sxs-lookup"><span data-stu-id="c2ff9-213">Dates, Year offset</span></span>                                    |

<span data-ttu-id="c2ff9-214">Per impostazione predefinita, il contenuto mostra i dati dell'anno di calendario corrente.</span><span class="sxs-lookup"><span data-stu-id="c2ff9-214">By default, the content shows data for the current calendar year.</span></span> <span data-ttu-id="c2ff9-215">Tuttavia, è possibile modificare il filtro della data nella sezione relativa ai filtri di report.</span><span class="sxs-lookup"><span data-stu-id="c2ff9-215">However, you can change the date filter in the report filters section.</span></span> <span data-ttu-id="c2ff9-216">È inoltre possibile modificare il filtro della società.</span><span class="sxs-lookup"><span data-stu-id="c2ff9-216">You can also change the company filter.</span></span>
