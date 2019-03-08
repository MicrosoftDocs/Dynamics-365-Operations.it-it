---
title: Contenuto Power BI sull'analisi delle spese di acquisto
description: In questo argomento viene descritto cosa è incluso nel contenuto di Power BI per l'analisi delle spese di acquisto. Viene descritto come accedere ai report inclusi nel contenuto e vengono fornite informazioni sul modello dati e sulle entità utilizzati per creare il contenuto.
author: FrankDahl
manager: AnnBe
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: PurchaseSpendAnalysisPowerBI
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 069c4dc21959ab603ba6ca3da0ac68ef20325265
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "313844"
---
# <a name="purchase-spend-analysis-power-bi-content"></a><span data-ttu-id="8f06b-104">Contenuto Power BI sull'analisi delle spese di acquisto</span><span class="sxs-lookup"><span data-stu-id="8f06b-104">Purchase spend analysis Power BI content</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8f06b-105">In questo argomento viene descritto cosa è incluso nel contenuto di Power BI **Analisi delle spese di acquisto**.</span><span class="sxs-lookup"><span data-stu-id="8f06b-105">This topic describes what is included in the **Purchase spend analysis** Microsoft Power BI content.</span></span> <span data-ttu-id="8f06b-106">Descrive come accedere ai report di Power BI e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto.</span><span class="sxs-lookup"><span data-stu-id="8f06b-106">It explains how to access the Power BI reports, and provides information about the data model and entities that are used to build the content.</span></span>

## <a name="overview"></a><span data-ttu-id="8f06b-107">Panoramica</span><span class="sxs-lookup"><span data-stu-id="8f06b-107">Overview</span></span>

<span data-ttu-id="8f06b-108">Il contenuto di Power BI **Analisi delle spese di acquisto** è stato progettato per consentire ai responsabili acquisti e i dirigenti responsabili di budget di tenere sotto controllo la spesa di acquisto.</span><span class="sxs-lookup"><span data-stu-id="8f06b-108">The **Purchase spend analysis** Power BI content was designed to help purchasing managers and managers who are responsible for budgets keep an eye on purchase spending.</span></span> <span data-ttu-id="8f06b-109">I responsabili possono analizzare la spesa d'acquisto nei seguenti modi:</span><span class="sxs-lookup"><span data-stu-id="8f06b-109">Managers can analyze purchase spending in the following ways:</span></span>

- <span data-ttu-id="8f06b-110">Acquisto da inizio anno (per gruppo di fornitori e singoli fornitori, per categoria di approvvigionamento e singoli prodotti e per ubicazione del fornitore)</span><span class="sxs-lookup"><span data-stu-id="8f06b-110">Year-to-date purchase (by vendor group and individual vendors, procurement category and individual products, and vendor location)</span></span>
- <span data-ttu-id="8f06b-111">Modifica di acquisto da inizio anno (per gruppo di fornitori e categoria di approvvigionamento)</span><span class="sxs-lookup"><span data-stu-id="8f06b-111">Year-over-year purchase change (by vendor group and procurement category)</span></span>

<span data-ttu-id="8f06b-112">Il contenuto utilizza dati transazionali di acquisto e offre sia una visualizzazione aggregata delle cifre di acquisto a livello di società che una scomposizione dettagliata della spesa di acquisto per fornitore e prodotto.</span><span class="sxs-lookup"><span data-stu-id="8f06b-112">The content uses purchase transactional data, and provides both an aggregate view of the company-wide purchase figures and a breakdown of purchase spending by vendor and product.</span></span> <span data-ttu-id="8f06b-113">I report evidenziano le modifiche nella spesa di acquisto nel tempo.</span><span class="sxs-lookup"><span data-stu-id="8f06b-113">Reports highlight changes in purchase spending over time.</span></span> <span data-ttu-id="8f06b-114">Di conseguenza, è possibile utilizzarli per avvisare i responsabili sulle tendenze positive e negative di spesa per singoli fornitori e prodotti.</span><span class="sxs-lookup"><span data-stu-id="8f06b-114">Therefore, the reports can be used to alert managers about positive and negative spending trends for individual vendors and products.</span></span> <span data-ttu-id="8f06b-115">Inoltre, i grafici mostrano la spesa di acquisto per categorie di approvvigionamento e gruppi di fornitori diversi.</span><span class="sxs-lookup"><span data-stu-id="8f06b-115">Additionally, charts show purchase spending for different procurement categories and vendor groups.</span></span> <span data-ttu-id="8f06b-116">Pertanto, i responsabili di categoria e regionali possono usare questi grafici per identificare i cambiamenti nel comportamento di spesa.</span><span class="sxs-lookup"><span data-stu-id="8f06b-116">Therefore, category and regional managers can use the charts to help identify changes in spending behavior.</span></span>

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="8f06b-117">Accesso al contenuto Power BI</span><span class="sxs-lookup"><span data-stu-id="8f06b-117">Accessing the Power BI content</span></span>
<span data-ttu-id="8f06b-118">Il contenuto di Power BI **Analisi delle spese di acquisto** viene mostrato nella pagina **Analisi di spesa e acquisto** (**Approvvigionamento** \> **Richieste di informazioni e report** \> **Analisi delle prestazioni di acquisto** \> **Analisi delle prestazioni di acquisto**).</span><span class="sxs-lookup"><span data-stu-id="8f06b-118">The **Purchase spend analysis** Power BI content is shown on the **Purchase and spend analysis** page (**Procurement and sourcing** \> **Inquiries and reports** \> **Purchase performance analysis** \> **Purchase and spend analysis**).</span></span>

## <a name="metrics-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="8f06b-119">Metriche incluse nel contenuto Power BI</span><span class="sxs-lookup"><span data-stu-id="8f06b-119">Metrics that are included in the Power BI content</span></span>
<span data-ttu-id="8f06b-120">Il contenuto di Power BI **Analisi delle spese di acquisto** include un report costituito da un set di metriche.</span><span class="sxs-lookup"><span data-stu-id="8f06b-120">The **Purchase spend analysis** Power BI content includes a report that consists of a set of metrics.</span></span> <span data-ttu-id="8f06b-121">Queste metriche vengono visualizzate come grafici, riquadri e tabelle.</span><span class="sxs-lookup"><span data-stu-id="8f06b-121">These metrics are visualized as charts, tiles, and tables.</span></span> <span data-ttu-id="8f06b-122">Nella seguente tabella viene fornita una panoramica delle visualizzazioni.</span><span class="sxs-lookup"><span data-stu-id="8f06b-122">The following table provides an overview of the visualizations.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="8f06b-123">Pagina di report</span><span class="sxs-lookup"><span data-stu-id="8f06b-123">Report page</span></span></th>
<th><span data-ttu-id="8f06b-124">Grafici</span><span class="sxs-lookup"><span data-stu-id="8f06b-124">Charts</span></span></th>
<th><span data-ttu-id="8f06b-125">Riquadri</span><span class="sxs-lookup"><span data-stu-id="8f06b-125">Tiles</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="8f06b-126">Acquisti per fornitore</span><span class="sxs-lookup"><span data-stu-id="8f06b-126">Purchase by vendor</span></span></td>
<td><ul>
<li><span data-ttu-id="8f06b-127">Primi 10 fornitori per acquisti (grafico a barre impilate)</span><span class="sxs-lookup"><span data-stu-id="8f06b-127">Top 10 vendors by purchase (stacked bar chart)</span></span></li>
<li><span data-ttu-id="8f06b-128">Acquisti totali per gruppo di fornitori/paese/nome (grafico a torta)</span><span class="sxs-lookup"><span data-stu-id="8f06b-128">Total purchase by vendor group / country / name (pie chart)</span></span></li>
<li><span data-ttu-id="8f06b-129">Acquisti per gruppo di fornitori/paese/nome (istogramma)</span><span class="sxs-lookup"><span data-stu-id="8f06b-129">Purchase by vendor group / country / name (column chart)</span></span></li>
<li><span data-ttu-id="8f06b-130">Media degli acquisti per gruppo di fornitori/paese/nome (istogramma)</span><span class="sxs-lookup"><span data-stu-id="8f06b-130">Average purchase by vendor group / country / name (column chart)</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="8f06b-131">Totale acquisto</span><span class="sxs-lookup"><span data-stu-id="8f06b-131">Total purchase</span></span></li>
<li><span data-ttu-id="8f06b-132">Crescita degli acquisti su base annua</span><span class="sxs-lookup"><span data-stu-id="8f06b-132">YOY purchase growth</span></span></li>
<li><span data-ttu-id="8f06b-133">N. totale fornitori</span><span class="sxs-lookup"><span data-stu-id="8f06b-133">Total # vendors</span></span></li>
<li><span data-ttu-id="8f06b-134">N. totale dei fornitori attivi</span><span class="sxs-lookup"><span data-stu-id="8f06b-134">Total # of active vendors</span></span></li>
</ul></td>
</tr>
<tr>
<td><span data-ttu-id="8f06b-135">Acquisti per prodotto</span><span class="sxs-lookup"><span data-stu-id="8f06b-135">Purchase by product</span></span></td>
<td><ul>
<li><span data-ttu-id="8f06b-136">Acquisti per categoria di approvvigionamento/nome prodotto (istogramma)</span><span class="sxs-lookup"><span data-stu-id="8f06b-136">Purchase by procurement category / product name (column chart)</span></span></li>
<li><span data-ttu-id="8f06b-137">Acquisti totali per categoria di approvvigionamento/nome prodotto (grafico a torta)</span><span class="sxs-lookup"><span data-stu-id="8f06b-137">Total purchase by procurement category / product name (pie chart)</span></span></li>
<li><span data-ttu-id="8f06b-138">Primi 10 prodotti per acquisti (grafico a barre impilate)</span><span class="sxs-lookup"><span data-stu-id="8f06b-138">Top 10 products by purchase (stacked bar chart)</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="8f06b-139">N. totale di prodotti</span><span class="sxs-lookup"><span data-stu-id="8f06b-139">Total # of products</span></span></li>
<li><span data-ttu-id="8f06b-140">Percentuale di prodotti attivi totali del numero totale di prodotti</span><span class="sxs-lookup"><span data-stu-id="8f06b-140">Total active products percentage of total # of products</span></span></li>
<li><span data-ttu-id="8f06b-141">Numero di prodotti che rappresentano l'80% degli acquisti</span><span class="sxs-lookup"><span data-stu-id="8f06b-141">Number of products accounting for 80% purchase</span></span></li>
</ul></td>
</tr>
<tr>
<td><span data-ttu-id="8f06b-142">Acquisti per periodo\*</span><span class="sxs-lookup"><span data-stu-id="8f06b-142">Purchase by period\*</span></span></td>
<td><ul>
<li><span data-ttu-id="8f06b-143">Acquisti al mese/giorno (istogramma)</span><span class="sxs-lookup"><span data-stu-id="8f06b-143">Purchase by month / day (column chart)</span></span></li>
<li><span data-ttu-id="8f06b-144">Scostamento di acquisti cumulativi su base annua (grafico a cascata)</span><span class="sxs-lookup"><span data-stu-id="8f06b-144">Cumulative purchase YOY variance (waterfall chart)</span></span></li>
<li><span data-ttu-id="8f06b-145">Crescita degli acquisti totali su base annua (istogramma)</span><span class="sxs-lookup"><span data-stu-id="8f06b-145">Total purchase YOY growth (column chart)</span></span></li>
<li><span data-ttu-id="8f06b-146">Rendiconto di approvvigionamento (matrice)</span><span class="sxs-lookup"><span data-stu-id="8f06b-146">Procurement statement (matrix)</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="8f06b-147">Crescita degli acquisti su base annua</span><span class="sxs-lookup"><span data-stu-id="8f06b-147">YOY purchase growth</span></span></li>
<li><span data-ttu-id="8f06b-148">% di crescita degli acquisti su base annua</span><span class="sxs-lookup"><span data-stu-id="8f06b-148">YOY purchase growth %</span></span></li>
</ul></td>
</tr>
<tr>
<td><span data-ttu-id="8f06b-149">Acquisti per ubicazione del fornitore</span><span class="sxs-lookup"><span data-stu-id="8f06b-149">Purchase by vendor location</span></span></td>
<td><ul>
<li><span data-ttu-id="8f06b-150">Acquisti per città</span><span class="sxs-lookup"><span data-stu-id="8f06b-150">Purchase by city</span></span></li>
<li><span data-ttu-id="8f06b-151">% di crescita su base annua degli acquisti</span><span class="sxs-lookup"><span data-stu-id="8f06b-151">Purchase YOY growth %</span></span></li>
<li><span data-ttu-id="8f06b-152">Acquisti per paese</span><span class="sxs-lookup"><span data-stu-id="8f06b-152">Purchase by country</span></span></li>
</ul></td>
<td></td>
</tr>
<tr>
<td><span data-ttu-id="8f06b-153">Analisi delle spese di acquisto in base all'ora</span><span class="sxs-lookup"><span data-stu-id="8f06b-153">Purchase spend analysis by time</span></span></td>
<td><ul>
<li><span data-ttu-id="8f06b-154">Acquisti nell'anno corrente al mese/giorno (grafico a linee)</span><span class="sxs-lookup"><span data-stu-id="8f06b-154">Purchase current year by month / day (line chart)</span></span></li>
<li><span data-ttu-id="8f06b-155">Acquisti nell'anno corrente e nell'anno passato (grafico a linee e colonne)</span><span class="sxs-lookup"><span data-stu-id="8f06b-155">Purchase current and last year (line and column chart)</span></span></li>
</ul></td>
<td></td>
</tr>
<tr>
<td><span data-ttu-id="8f06b-156">Analisi delle spese di acquisto per fornitore</span><span class="sxs-lookup"><span data-stu-id="8f06b-156">Purchase spend analysis by vendor</span></span></td>
<td><ul>
<li><span data-ttu-id="8f06b-157">% di acquisti dei primi 10 fornitori (grafico a imbuto)</span><span class="sxs-lookup"><span data-stu-id="8f06b-157">Top 10 vendor purchase % of purchase (funnel)</span></span></li>
<li><span data-ttu-id="8f06b-158">Primi 10 fornitori con aumento delle spese su base annua</span><span class="sxs-lookup"><span data-stu-id="8f06b-158">Top 10 vendors with increased spending YOY</span></span></li>
<li><span data-ttu-id="8f06b-159">Primi 10 fornitori con diminuzione delle spese su base annua</span><span class="sxs-lookup"><span data-stu-id="8f06b-159">Top 10 vendors with decreased spending YOY</span></span></li>
</ul></td>
<td></td>
</tr>
</tbody>
</table>

<span data-ttu-id="8f06b-160">\* Acquisti nell'anno corrente e nell'anno passato e crescita per categoria di approvvigionamento</span><span class="sxs-lookup"><span data-stu-id="8f06b-160">\* Purchase this year and last year, and growth by procurement category</span></span>

## <a name="data-model-and-entities"></a><span data-ttu-id="8f06b-161">Modello dati ed entità</span><span class="sxs-lookup"><span data-stu-id="8f06b-161">Data model and entities</span></span>
<span data-ttu-id="8f06b-162">I seguenti dati vengono utilizzati per compilare le pagine di report nel contenuto Power BI **Analisi delle spese di acquisto**.</span><span class="sxs-lookup"><span data-stu-id="8f06b-162">The following data is used to fill the report pages in the **Purchase spend analysis** Power BI content.</span></span> <span data-ttu-id="8f06b-163">Questi dati vengono rappresentati come misure aggregate approntate nell'archivio entità.</span><span class="sxs-lookup"><span data-stu-id="8f06b-163">This data is represented as aggregate measurements that are staged in the Entity store.</span></span> <span data-ttu-id="8f06b-164">L'archivio entità è un database di Microsoft SQL Server che viene ottimizzato per l'analisi dei dati.</span><span class="sxs-lookup"><span data-stu-id="8f06b-164">The Entity store is a Microsoft SQL Server database that is optimized for analytics.</span></span> <span data-ttu-id="8f06b-165">Per ulteriori informazioni, vedere [Panoramica dell'integrazione di Power BI con l'archivio entità](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="8f06b-165">For more information, see [Overview of Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span>

<span data-ttu-id="8f06b-166">Le misure di aggregazione in questo pacchetto di contenuti sono il sottoinsieme delle misure di aggregazione disponibili nel cubo Acquisiti in Microsoft Dynamics AX 2012 e Microsoft Dynamics AX 2012 R3.</span><span class="sxs-lookup"><span data-stu-id="8f06b-166">The aggregate measurements in this content are the subset of aggregate measurements that were available in the Purchase Cube in Microsoft Dynamics AX 2012 and Microsoft Dynamics AX 2012 R3.</span></span> <span data-ttu-id="8f06b-167">Per rappresentare le misure di aggregazione del cubo nell'Archivio entità, è necessario renderle distribuibili.</span><span class="sxs-lookup"><span data-stu-id="8f06b-167">To stage the cube's aggregate measurements in the Entity store, you must make them deployable.</span></span> <span data-ttu-id="8f06b-168">Per ulteriori informazioni, vedere la procedura per la rappresentazione delle misure di aggregazione nell'Archivio entità in [Panoramica dell'integrazione di Power BI con l'archivio entità](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="8f06b-168">For more information, see the procedure for staging aggregate measurements in the Entity store in [Overview of Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span> <span data-ttu-id="8f06b-169">Le seguenti misure di aggregazione chiave sono disponibili direttamente dall'entità delle righe della fattura e sono utilizzate come base del contenuto.</span><span class="sxs-lookup"><span data-stu-id="8f06b-169">The following key aggregate measurements are available directly from the Invoice lines entity and are used as the basis of the content.</span></span>

| <span data-ttu-id="8f06b-170">Entità</span><span class="sxs-lookup"><span data-stu-id="8f06b-170">Entity</span></span>        | <span data-ttu-id="8f06b-171">Misure di aggregazione chiave</span><span class="sxs-lookup"><span data-stu-id="8f06b-171">Key aggregate measurements</span></span> | <span data-ttu-id="8f06b-172">Origine dati</span><span class="sxs-lookup"><span data-stu-id="8f06b-172">Data source</span></span>                                 | <span data-ttu-id="8f06b-173">Campo</span><span class="sxs-lookup"><span data-stu-id="8f06b-173">Field</span></span>              | <span data-ttu-id="8f06b-174">descrizione</span><span class="sxs-lookup"><span data-stu-id="8f06b-174">Description</span></span>                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| <span data-ttu-id="8f06b-175">Righe fattura</span><span class="sxs-lookup"><span data-stu-id="8f06b-175">Invoice lines</span></span> | <span data-ttu-id="8f06b-176">Acquisti</span><span class="sxs-lookup"><span data-stu-id="8f06b-176">Purchase</span></span>                   | <span data-ttu-id="8f06b-177">VendInvoiceTrans</span><span class="sxs-lookup"><span data-stu-id="8f06b-177">VendInvoiceTrans</span></span>                            | <span data-ttu-id="8f06b-178">SUM(LineAmountMST)</span><span class="sxs-lookup"><span data-stu-id="8f06b-178">SUM(LineAmountMST)</span></span> | <span data-ttu-id="8f06b-179">Importo nella valuta di contabilizzazione.</span><span class="sxs-lookup"><span data-stu-id="8f06b-179">The amount in the accounting currency.</span></span> |

<span data-ttu-id="8f06b-180">Nella seguente tabella vengono illustrate le misurazioni chiave nel contenuto calcolate dall'entità delle righe della fattura.</span><span class="sxs-lookup"><span data-stu-id="8f06b-180">The following table shows the key measurements in the content that are calculated from the Invoice lines entity.</span></span>

| <span data-ttu-id="8f06b-181">Unità di misura</span><span class="sxs-lookup"><span data-stu-id="8f06b-181">Measure</span></span>               | <span data-ttu-id="8f06b-182">Calcolo</span><span class="sxs-lookup"><span data-stu-id="8f06b-182">Calculation</span></span>                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| <span data-ttu-id="8f06b-183">Acquisti nell'anno corrente</span><span class="sxs-lookup"><span data-stu-id="8f06b-183">Purchase current year</span></span> | <span data-ttu-id="8f06b-184">Acquisto nell'anno corrente = SUM('Righe fattura'\[Acquisti\])</span><span class="sxs-lookup"><span data-stu-id="8f06b-184">Purchase current year = SUM('Invoice lines'\[Purchase\])</span></span>                                            |
| <span data-ttu-id="8f06b-185">Acquisti nell'anno passato</span><span class="sxs-lookup"><span data-stu-id="8f06b-185">Purchase last year</span></span>    | <span data-ttu-id="8f06b-186">Acquisti nell'anno passato = CALCULATE(SUM('Righe fattura'\[Acquisti\]), SAMEPERIODLASTYEAR(Dates\[Data\]))</span><span class="sxs-lookup"><span data-stu-id="8f06b-186">Purchase last year = CALCULATE(SUM('Invoice lines'\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\]))</span></span> |
| <span data-ttu-id="8f06b-187">Crescita degli acquisti su base annua</span><span class="sxs-lookup"><span data-stu-id="8f06b-187">YOY purchase growth</span></span>   | <span data-ttu-id="8f06b-188">Crescita degli acquisti su base annua = \[Acquisti nell'anno corrente\] - \[Acquisti nell'anno passato\]</span><span class="sxs-lookup"><span data-stu-id="8f06b-188">YOY purchase growth = \[Purchase current year\] – \[Purchase last year\]</span></span>                            |

<span data-ttu-id="8f06b-189">Le seguenti dimensioni chiave nel contenuto vengono utilizzate come filtri per dividere le misure di aggregazione in modo da poter ottenere una maggiore granularità e fornire informazioni analitiche più approfondite.</span><span class="sxs-lookup"><span data-stu-id="8f06b-189">The following key dimensions in the content are used as filters to slice the aggregate measurements, so that you can achieve more granularity and gain deeper analytical insights.</span></span>

| <span data-ttu-id="8f06b-190">Entità</span><span class="sxs-lookup"><span data-stu-id="8f06b-190">Entity</span></span>                 | <span data-ttu-id="8f06b-191">Esempi di attributi</span><span class="sxs-lookup"><span data-stu-id="8f06b-191">Examples of attributes</span></span>                                |
|------------------------|-------------------------------------------------------|
| <span data-ttu-id="8f06b-192">Fornitori</span><span class="sxs-lookup"><span data-stu-id="8f06b-192">Vendors</span></span>                | <span data-ttu-id="8f06b-193">Gruppi di fornitori, paese o regioni del fornitore, nome del fornitore</span><span class="sxs-lookup"><span data-stu-id="8f06b-193">Vendor groups, Vendor country or regions, Vendor name</span></span> |
| <span data-ttu-id="8f06b-194">Prodotti</span><span class="sxs-lookup"><span data-stu-id="8f06b-194">Products</span></span>               | <span data-ttu-id="8f06b-195">Numero prodotto, nome prodotto, nome dei gruppi di articoli</span><span class="sxs-lookup"><span data-stu-id="8f06b-195">Product number, Product name, Item groups name</span></span>        |
| <span data-ttu-id="8f06b-196">Categorie di approvvigionamento</span><span class="sxs-lookup"><span data-stu-id="8f06b-196">Procurement categories</span></span> | <span data-ttu-id="8f06b-197">Categoria di approvvigionamento, nomi delle categorie di approvvigionamento</span><span class="sxs-lookup"><span data-stu-id="8f06b-197">Procurement category, Procurement category names</span></span>      |
| <span data-ttu-id="8f06b-198">Persone giuridiche</span><span class="sxs-lookup"><span data-stu-id="8f06b-198">Legal entities</span></span>         | <span data-ttu-id="8f06b-199">Nome persona giuridica</span><span class="sxs-lookup"><span data-stu-id="8f06b-199">Legal entity name</span></span>                                     |
| <span data-ttu-id="8f06b-200">Appuntamenti</span><span class="sxs-lookup"><span data-stu-id="8f06b-200">Dates</span></span>                  | <span data-ttu-id="8f06b-201">Date, offset anno</span><span class="sxs-lookup"><span data-stu-id="8f06b-201">Dates, Year offset</span></span>                                    |

<span data-ttu-id="8f06b-202">Per impostazione predefinita, il contenuto mostra i dati dell'anno di calendario corrente.</span><span class="sxs-lookup"><span data-stu-id="8f06b-202">By default, the content shows data for the current calendar year.</span></span> <span data-ttu-id="8f06b-203">Tuttavia, è possibile modificare il filtro della data nella sezione relativa ai filtri di report.</span><span class="sxs-lookup"><span data-stu-id="8f06b-203">However, you can change the date filter in the report filters section.</span></span> <span data-ttu-id="8f06b-204">È inoltre possibile modificare il filtro della società.</span><span class="sxs-lookup"><span data-stu-id="8f06b-204">You can also change the company filter.</span></span>
