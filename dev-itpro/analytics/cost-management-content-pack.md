---
title: Contenuto Power BI per la gestione dei costi
description: "In questo argomento viene descritto cosa è incluso nel contenuto Power BI per la gestione dei costi. Descrive come accedere ai report di Power BI e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations
ms.custom: 270314
ms.assetid: 9680d977-43c8-47a7-966d-2280ba21402a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: a9449e42224d5dfb1bc1f0368a041c45afc334a2
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="cost-management-power-bi-content"></a>Contenuto Power BI per la gestione dei costi

[!include[banner](../includes/banner.md)]


In questo argomento viene descritto cosa è incluso nel contenuto Power BI per la gestione dei costi. Descrive come accedere ai report di Power BI e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto.

# <a name="overview"></a>Panoramica

I contenuto Microsoft Power BI per la **gestione dei costi** è destinato ai contabili di inventario o agli utenti dell'organizzazione responsabili per l'inventario. Il contenuto Power BI per la **gestione dei costi** fornisce analisi manageriali dell'inventario e delle scorte WIP e di come il costo procede attraverso questi per categoria nel tempo. Le informazioni possono essere utilizzate anche come supplemento dettagliato al rendiconto finanziario.

## <a name="key-measures"></a>Misure chiave

+ Saldo iniziale
+ Saldo finale
+ Modifica netto
+ Modifica netto in %
+ Aging

## <a name="key-performance-indicators"></a>Indicatori di prestazioni chiave
+ Rotazione scorte
+ Precisione inventario

L'origine dati principale per CostAggregatedCostStatementEntryEntity è la tabella CostStatementCache. Questa tabella viene gestita dal framework della cache del set di dati. Per impostazione predefinita, la tabella viene aggiornata ogni 24 ore, ma è possibile abilitare gli aggiornamenti manuali nella configurazione della cache di dati. È possibile poi eseguire un aggiornamento manuale nell'area di lavoro **Gestione costi** o **Analisi costo**. Dopo l'aggiornamento di CostStatementCache, è necessario aggiornare la connessione OData su Power BI.com per visualizzare i dati aggiornati nel sito. Le misure di scostamento (acquisto, produzione) nel contenuto di Power BI coprono solo gli articoli che vengono valutati con il metodo di inventario costo standard. Lo scostamento di produzione viene calcolato come la differenza tra i costi attivi e costo realizzato. Lo scostamento di produzione viene calcolato quando l'ordine di produzione ha lo stato **Finito**. Per ulteriori informazioni sui tipi di scostamento produzione e come ciascun tipo viene calcolato, vedere  [Informazioni sull'analisi degli scostamenti per un ordine di produzione completato](https://technet.microsoft.com/en-us/library/gg242850.aspx).

## <a name="accessing-the-power-bi-content"></a>Accesso al contenuto Power BI
Il contenuto Power BI per la **gestione dei costi** è disponibile da PowerBI.com. Per ulteriori informazioni su come connettere e collegare i dati di Microsoft Dynamics 365 for Operations, vedere [Accedere al contenuto Power BI da PowerBI.com](power-bi-home-page.md).

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Metriche incluse nel contenuto Power BI
Il contenuto include un set di pagine di report. Ciascuna pagina è costituita da un set di metriche visualizzate come grafici, riquadri e tabelle. Nella seguente tabella viene fornita una panoramica delle visualizzazioni nel contenuto Power BI per la **gestione dei costi**.

| Pagina di report | Grafici | Titoli |
|---|---|---|
|Inventario complessivo (predefinito per periodo corrente) |Precisione |Misure di inventario:<br>Saldo finale inventario<br>Modifica netto inventario<br>% modifica netto inventario<br>|
| |Rotazione scorte | |
| |Saldo finale inventario per gruppo di risorse | |
| |Modifica netto inventario per nome categoria livello 1 e nome categoria livello 2| |
| |Scostamenti acquisto per gruppo di risorse e nome categoria livello 3 | |
|Inventario per sito (predefinito per periodo corrente) |Saldo finale inventario per nome sito e gruppo di risorse | |
| |Rotazione scorte per nome sito e gruppo di risorse | |
| |Saldo finale inventario per città e gruppo di risorse | |
|Inventario per gruppo di risorse (predefinito per periodo corrente) |Misure di inventario | |
| |Precisione inventario per importo per gruppo di risorse | |
| |Rotazione scorte per importo per gruppo di risorse | |
|Inventario su base annua (predefinito anno corrente rispetto a precedente ) |Misure di inventario | |
| |KPI inventario:<br>Rotazione scorte<br>Precisione inventario | |
| |Saldo finale inventario per anno e gruppo di risorse | |
| |Scostamenti acquisto per anno e nome categoria livello 3 | |
|Aging inventario (predefinito per anno corrente) |Aging inventario per trimestre e gruppo di risorse | |
| |Aging inventario per trimestre e nome sito | |
|WIP complessivo (predefinito per periodo corrente) |Modifica netto WIP per nome categoria livello 1 e nome categoria livello 2 |Misure WIP semilavorati:<br>Saldo finale WIP<br>Modifica netto WIP<br>% modifica netto WIP<br> |
| |Scostamenti produzione per gruppo di risorse e nome categoria livello 3 | |
| |Modifica netto WIP per gruppo di risorse | |
|WIP per sito (predefinito per periodo corrente) |Misure WIP semilavorati | |
| |Modifica netto WIP per nome sito e nome categoria livello 2 | |
| |Scostamenti produzione per nome sito e nome categoria livello 3 | |

## <a name="understanding-the-data-model-and-entities"></a>Informazioni su modelli ed entità di dati
I dati di Dynamics 365 for Operations vengono utilizzati per compilare le pagine di report nel contenuto Power BI per la **gestione dei costi**. Questi dati sono rappresentati come misure aggregate che vengono collocate nell'archivio entità, ovvero un database di Microsoft SQL ottimizzato per l'analisi. Per ulteriori informazioni, vedere [Panoramica dell'integrazione di Power BI con l'archivio entità](power-bi-integration-entity-store.md). Le seguenti misure aggregazione chiave vengono utilizzate come base del contenuto.

| Entità            | Misura di aggregazione chiave | Origine dati per Dynamics 365 for Operations | Campo             | descrizione                       |
|-------------------|---------------------------|---------------------------------------------|-------------------|-----------------------------------|
| Voci di rendiconto | Modifica netto                | CostAggregatedCostStatementEntryEntity      | sum(\[Importo\])   | Importo nella valuta di contabilizzazione |
| Voci di rendiconto | Quantità modifica netto       | CostAggregatedCostStatementEntryEntity      | sum(\[Quantità\]) |                                   |

Nella tabella seguente vengono illustrate le misure di aggregazione chiave utilizzate per creare diverse misure calcolate nel set di dati del contenuto.

| Unità di misura                                 | Come la misura viene calcolata                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Saldo iniziale                       | \[Saldo finale\]-\[Modifica netto\]                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Quantità saldo iniziale              | \]Quantità saldo finale\]-\[Quantità modifica netto\[                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Saldo finale                          | CALCULATE(SUM(\[Importo\]), FILTER(ALLEXCEPT('Calendari fiscali', 'Calendari fiscali'\[LedgerRecId\], 'entità'\[ID\], 'entità'\[Nome\], 'Contabilità generali'\[Valuta\], 'Contabilità generali'\[Descrizione\], 'Contabilità generali'\[Nome\]), 'Calendari fiscali'\[Data\] &lt;= MAX('Calendari fiscali'\[Data\])))                                                                                                                                                                                           |
| Quantità saldo finale                 | CALCULATE(SUM(\[Quantità\]), FILTER(ALLEXCEPT('Calendari fiscali', 'Calendari fiscali'\[LedgerRecId\], 'entità'\[ID\], 'entità'\[Nome\], 'Contabilità generali'\[Valuta\], 'Contabilità generali'\[Descrizione\], 'Contabilità generali'\[Nome\]), 'Calendari fiscali'\[Data\] &lt;= MAX('Calendari fiscali'\[Data\])))                                                                                                                                                                                         |
| Saldo iniziale inventario             | CALCULATE(\[Saldo iniziale\], 'Voci rendiconto'\[Tipo rendiconto\] = "Inventario")                                                                                                                                                                                                                                                                                                                                                                                      |
| Saldo finale inventario                | CALCULATE(\[Saldo finale\], 'Voci rendiconto'\[Tipo rendiconto\] = "Inventario")                                                                                                                                                                                                                                                                                                                                                                                         |
| Modifica netto inventario                    | CALCULATE(\[Modifica netto\], 'Voci rendiconto'\[Tipo rendiconto\] = "Inventario")                                                                                                                                                                                                                                                                                                                                                                                             |
| Quantità modifica netto inventario           | CALCULATE(\[Quantità modifica netto\], 'Voci rendiconto'\[Tipo rendiconto\] = "Inventario")                                                                                                                                                                                                                                                                                                                                                                                    |
| % modifica netto inventario                  | IF(\[Saldo finale inventario\] = 0, 0, \[Modifica netto inventario\] / \[Saldo finale inventario\])                                                                                                                                                                                                                                                                                                                                                                           |
| Rotazione scorte per importo                | if(OR(\[Saldo medio inventario\] &lt;= 0, \[Inventario venduto o uscite consumate\] &gt;= 0), 0, ABS(\[Inventario venduto o uscite consumate\])/\[Saldo medio inventario\])                                                                                                                                                                                                                                                                                                  |
| Saldo medio inventario               | (\[Saldo finale inventario\] + \[Saldo iniziale inventario\]) / 2                                                                                                                                                                                                                                                                                                                                                                                                       |
| Inventario venduto o uscite consumate       | \[Inventario venduto\] + \[Costo materiale inventario consumato\]                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Costo materiale inventario consumato        | CALCULATE(\[Modifica netto inventario\], 'Voci rendiconto'\[Nome categoria - livello 2\_\] = "ConsumedMaterialsCost")                                                                                                                                                                                                                                                                                                                                                            |
| Inventario venduto                          | CALCULATE(\[Modifica netto inventario\], 'Voci rendiconto'\[Nome categoria - livello 2\_\] = "Venduto")                                                                                                                                                                                                                                                                                                                                                                             |
| Precisione inventario per importo            | IF(\[Saldo finale inventario\] &lt;= 0, IF(OR(\[Importo conteggiato inventario\] &lt;&gt; 0, \[Saldo finale inventario\] &lt; 0), 0, 1), MAX(0, (\[Saldo finale inventario\] - ABS(\[Importo conteggiato inventario\]))/\[Saldo finale inventario\]))                                                                                                                                                                                                                              |
| Importo conteggiato inventario                | CALCULATE(\[Modifica netto inventario\], 'Voci rendiconto'\[Nome categoria - livello 3\_\] = "Conteggio")                                                                                                                                                                                                                                                                                                                                                                         |
| Aging delle scorte                         | if(ISBLANK(max('Calendari fiscali'\[Data\])), blank(), MAX(0, MIN(\[Quantità entrate aging inventario\], \[Quantità saldo finale aging inventario\] - \[Quantità entrate aging inventario nel futuro\]))) \* \[Costo unitario medio inventario\]                                                                                                                                                                                                                                |
| Quantità di entrate aging inventario       | IF(\[minDate\] = \[minDateAllSelected\], CALCULATE(\[Quantità modifica netto inventario\], 'Voci rendiconto'\[Quantità\] &gt; 0, FILTER(ALLEXCEPT('Calendari fiscali', 'Calendari fiscali'\[LedgerRecId\], 'entità'\[ID\], 'entità'\[Nome\], 'Contabilità generali'\[Valuta\], 'Contabilità generali'\[Descrizione\], 'Contabilità generali'\[Nome\]), 'Calendari fiscali'\[Data\] &lt;= MAX('Calendari fiscali'\[Data\]))), CALCULATE(\[Quantità modifica netto inventario\], 'Voci rendiconto'\[Quantità\] &gt; 0)) |
| Quantità saldo finale aging inventario | \[Quantità saldo finale inventario\] + CALCULATE(\[Quantità modifica netto inventario\], FILTER(ALLEXCEPT('Calendari fiscali', 'Calendari fiscali'\[LedgerRecId\], 'entities'\[ID\], 'entità'\[Nome\], 'Contabilità generali'\[Valuta\], 'Contabilità generali'\[Descrizione\], 'Contabilità generali'\[Nome\]), 'Calendari fiscali'\[Data\] &gt; max('Calendari fiscali'\[Data\]) ))                                                                                                                                 |
| Entrate aging inventario nel futuro  | CALCULATE(\[Modifica netto inventario\], 'Voci rendiconto'\[Importo\] &gt; 0, FILTER(ALLEXCEPT('Calendari fiscali', 'Calendari fiscali'\[LedgerRecId\], 'entità'\[ID\], 'entità'\[Nome\], 'Contabilità generali'\[Valuta\], 'Contabilità generali'\[Descrizione\], 'Contabilità generali'\[Nome\]), 'Calendari fiscali'\[Data\] &gt; MAX('Calendari fiscali'\[Data\])))                                                                                                                                             |
| Costo unitario medio inventario                 | CALCULATE(\[Saldo finale inventario\] / \[Quantità saldo finale inventario\],ALLEXCEPT('Calendari fiscali', 'Calendari fiscali'\[LedgerRecId\], 'entità'\[ID\], 'entità'\[Nome\], 'Contabilità generali'\[Valuta\], 'Contabilità generali'\[Descrizione\], 'Contabilità generali'\[Nome\]))                                                                                                                                                                                                                 |
| Scostamenti di acquisto                      | CALCULATE(SUM(\[Importo\]), 'Voci rendiconto'\[Nome categoria - livello 2\_\] = "Approvvigionato", 'Voci rendiconto'\[Tipo rendiconto\] = "Scostamento")                                                                                                                                                                                                                                                                                                                              |
| Saldo iniziale WIP                   | CALCULATE(\[Saldo iniziale\], 'Voci rendiconto'\[Tipo rendiconto\] = "WIP")                                                                                                                                                                                                                                                                                                                                                                                            |
| Saldo finale WIP                      | CALCULATE(\[Saldo finale\], 'Voci rendiconto'\[Tipo rendiconto\] = "WIP")                                                                                                                                                                                                                                                                                                                                                                                               |
| Modifica netto WIP                          | CALCULATE(\[Modifica netto\], 'Voci rendiconto'\[Tipo rendiconto\] = "WIP")                                                                                                                                                                                                                                                                                                                                                                                                   |
| % modifica netto WIP                        | IF(\[Saldo finale WIP\] = 0, 0, \[Modifica netto WIP\] / \[Saldo finale WIP\])                                                                                                                                                                                                                                                                                                                                                                                             |
| Scostamenti di produzione                    | CALCULATE(SUM(\[Importo\]), 'Voci rendiconto'\[Nome categoria - livello 2\_\] = "ManufacturedCost", 'Voci rendiconto'\[Tipo rendiconto\] = "Scostamento")                                                                                                                                                                                                                                                                                                                      |
| Nome categoria - livello 1                 | switch(\[Nome categoria - livello 1\_\], "None", "Nessuno", "NetSourcing", "Approvvigionamento netto", "NetUsage", "Utilizzo netto", "NetConversionCost", "Costo di conversione netto", "NetCostOfGoodsManufactured", "Costo netto merci", "BeginningBalance", "Saldo iniziale")                                                                                                                                                                                                         |
| Nome categoria - livello 2                 | switch(\[Nome categoria - livello 2\_\], "None", "Nessuno", "Procured", "Approvvigionato", "Disposed", "Dismesso", "Transferred", "Trasferito", "Sold", "Venduto", "ConsumedMaterialsCost", "Costo di materiali consumato", "ConsumedManufacturingCost", "Costo di produzione consumato", "ConsumedOutsourcingCost", "Costo di outsourcing consumato", "ConsumedIndirectCost", "Costi indiretti consumati", "ManufacturedCost", "Costo di produzione", "Variances", "Scostamenti")                            |
| Nome categoria - livello 3                 | switch(\[Nome categoria - livello 3\_\], "None", "Nessuno", "Counting", "Nessuno", "ProductionPriceVariance", "Prezzo di produzione", "QuantityVariance", "Quantità", "SubstitutionVariance", "Sostituzione", "ScrapVariance", "Scarti", "LotSizeVariance", "Dimensioni lotto", "RevaluationVariance", "Rivalutazione", "PurchasePriceVariance", "Prezzo di acquisto", "CostChangeVariance", "Variazione costo", "RoundingVariance", "Scostamento arrotondamento")                                                   |

Le dimensioni chiave seguenti vengono utilizzate come filtri per dividere le misure di aggregazione e ottenere una maggiore granularità e fornire informazioni analitiche più approfondite.

| Entità           | Esempi di attributi                       |
|------------------|----------------------------------------------|
| Entità         | ID, Nome                                     |
| Calendari fiscali | Calendario, Mese, Periodo, Trimestre, Anno       |
| Obiettivi KPI        | Obiettivo precisione inventario, Obiettivo rotazione scorte |
| Contabilità generali          | Valuta, Nome, Descrizione                  |
| Siti            | ID, Nome, Paese, Città                      |

## <a name="additional-resources"></a>Risorse aggiuntive
Di seguito sono riportati alcuni collegamenti utili correlati alle entità e alla creazione di contenuto per Power BI:

-   [Entità di dati](..\data-entities\data-entities.md)
-   [Creazione di pacchetti di contenuti per l'organizzazione](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modellazione di dati tramite Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Aggiunta di riquadri Power BI ad aree di lavoro](configure-power-bi-integration.md)





