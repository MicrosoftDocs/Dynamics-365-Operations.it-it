---
title: Contenuto Prestazioni di produttività di Power BI
description: In questo articolo viene descritto cosa è incluso nel contenuto Prestazioni di produttività di Power BI.
author: AndersGirke
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.search.form: ProductionPerformancePowerBI
ms.openlocfilehash: 010b351023c8dee2f1242442c5846098374f18ca
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280806"
---
# <a name="production-performance-power-bi-content"></a>Contenuto Prestazioni di produttività di Power BI

[!include [banner](../includes/banner.md)]

In questo articolo viene descritto cosa è incluso nel contenuto **Prestazioni di produttività** di Microsoft Power BI. Descrive come accedere ai report di Power BI e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto.

## <a name="overview"></a>Panoramica

Il contenuto di Power BI **Prestazioni di produttività** è per i responsabili o gli utenti di produzione nell'organizzazione responsabili del controllo di produzione.

I report inclusi consentono di utilizzare Power BI per controllare le prestazioni delle operazioni di produzione in relazione a esecuzione puntuale, qualità e costi. I report utilizzano i dati transazionali dagli ordini di produzione e dagli ordini lotto e forniscono sia una visualizzazione aggregata delle metriche di produzione a livello aziendale e una suddivisione delle metriche per prodotto e risorsa.

Il contenuto Power BI evidenzia la capacità dell'organizzazione di completare la produzione in tempo e completamente. Le proiezioni sulle prestazioni future vengono effettuate sulla base dei piani di produzione. Report completi forniscono informazioni dettagliate dei difetti di prodotto causati dalla produzione e la percentuale di difetti per risorse e operazioni.

Il contenuto Power BI consente inoltre di analizzare gli scostamenti di produzione. Gli scostamenti di produzione vengono calcolati come la differenza tra costo stimato e costo realizzato. Gli scostamenti produzione vengono calcolati quando gli ordini di produzione o gli ordini lotto raggiungono lo stato **Finito**.

Il contenuto di Power BI **Prestazioni di produttività** include dati provenienti dagli ordini di produzione e dagli ordini lotto. I report non contengono dati che siano correlati alle produzioni kanban.

## <a name="accessing-the-power-bi-content"></a>Accesso al contenuto Power BI
Il contenuto di Power BI **Prestazioni di produttività** viene mostrato nella pagina **Prestazioni di produttività** (**Controllo produzione** \> **Richieste di informazioni e report** \> **Analisi delle prestazioni di produttività** \> **Prestazioni di produttività**). 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Metriche incluse nel contenuto Power BI

Il contenuto di Power BI **Prestazioni di produttività** include un insieme delle pagine del report. Ciascuna pagina è costituita da un set di metriche visualizzate come grafici, riquadri e tabelle.

Nella seguente tabella viene fornita una panoramica delle visualizzazioni incluse.

| Pagina di report                                | Grafici | Riquadri |
|--------------------------------------------|--------|-------|
| Prestazioni di produttività                     | <ul><li>Numero di produzione per data</li><li>Numero di produzioni per prodotto e gruppo di articoli</li><li>Numero di produzioni pianificate per data</li><li>Ultimi 10 prodotti per puntuale e completo</li></ul> | <ul><li>Ordini totali</li><li>% puntuale e completo</li><li>% incompleta</li><li>% in anticipo</li><li>% in ritardo</li></ul> |
| Difetti per prodotto                         | <ul><li>Percentuale articoli difettosi (ppm) per data</li><li>Percentuale articoli difettosi (ppm) per prodotto e gruppo di articoli</li><li>Quantità prodotta per data</li><li>Primi 10 prodotti per percentuale effettiva</li></ul> | <ul><li>Percentuale articoli difettosi (ppm)</li><li>Quantità difettosa</li><li>Quantità totale</li></ul> |
| Tendenza difetti per prodotto                   | Percentuale articoli difettosi (ppm) per quantità prodotta | Percentuale articoli difettosi (ppm) |
| Difetti per risorsa                        | <ul><li>Percentuale articoli difettosi (ppm) per data</li><li>Percentuale articoli difettosi (ppm) per risorsa e sito</li><li>Percentuale articoli difettosi (ppm) per operazione</li><li>Prime 10 risorse per percentuale articoli difettosi</li></ul> | Quantità difettosa |
| Tendenza difetti per risorsa                  | Percentuale articoli difettosi (ppm) per quantità lavorata | |
| Scostamenti produzione per determinazione costi per commessa | <ul><li>Scostamento di produzione per data e tipo di gruppo di costo</li><li>Scostamento di produzione per sito e tipo di gruppo di costo</li><li>Primi 10 prodotti con scostamento di produzione sfavorevole</li><li>Primi 10 scostamenti di produzione sfavorevole per risorsa</li></ul> | <ul><li>Costo realizzato</li><li>Scostamento produzione</li><li>% scostamento di produzione</li></ul> |


## <a name="understanding-the-data-model-and-entities"></a>Informazioni su modelli ed entità di dati

I seguenti dati vengono utilizzati per compilare le pagine di report nel contenuto di Power BI **Prestazioni di produttività**. Questi dati vengono rappresentati come misure aggregate approntate nell'archivio entità. L'archivio entità è un database di Microsoft SQL Server che viene ottimizzato per l'analisi dei dati. Per ulteriori informazioni sull'archivio entità, vedere [Integrazione di Power BI con l'Archivio entità](power-bi-integration-entity-store.md).

La tabella seguente mostra le misure di aggregazione chiave utilizzate come base del contenuto Power BI.

| Entità                   | Misure di aggregazione chiave  | Origine dati per app per la finanza e le operazioni | Campo              |
|--------------------------|-----------------------------|----------------------------------------|--------------------|
| CostCalculation          | CostAmount                  | ProdCalcTransExpanded                  | CostAmount         |
| CostCalculation          | CostMarkup                  | ProdCalcTransExpanded                  | CostMarkup         |
| CostCalculation          | ActualCostAmount            | ProdCalcTransExpanded                  | RealCostAmount     |
| CostCalculation          | RealCostAdjustment          | ProdCalcTransExpanded                  | RealCostAdjustment |
| RouteTransactions        | ErrorQuantity               | ProdRouteTransExpanded                 | QtyError           |
| RouteTransactions        | GoodQuantity                | ProdRouteTransExpanded                 | QtyGood            |
| ProductionOrder          | DaysDelayed                 | ProdTableExpanded                      | DaysDelayed        |
| ProductionOrder          | LeadTime                    | ProdTableExpanded                      | LeadTime           |
| ProductionOrder          | PlannedLeadTime             | ProdTableExpanded                      | PlannedLeadTime    |
| ProductionOrder          | ProductionOrderCount        | ProdTableExpanded                      |                    |
| CoproductCostCalculation | CoproductCostAmount         | PmfCoByProdCalcTransExpanded           | CostAmount         |
| CoproductCostCalculation | CoproductCostMarkup         | PmfCoByProdCalcTransExpanded           | CostMarkup         |
| CoproductCostCalculation | CoproductRealCostAdjustment | PmfCoByProdCalcTransExpanded           | RealCostAdjustment |
| CoproductCostCalculation | CoproductActualCostAmount   | PmfCoByProdCalcTransExpanded           | RealCostAmount     |

Nella tabella seguente vengono illustrate le misure di aggregazione chiave utilizzate per creare diverse misure calcolate nel set di dati del contenuto.

| Unità di misura                  | Come la misura viene calcolata |
|--------------------------|-------------------------------|
| Scostamento di produzione, %   | SUM('Scostamento produzione'\[Scostamento produzione\]) / SUM('Scostamento produzione'\[Costo stimato\]) |
| Tutti gli ordini pianificati       | COUNTROWS('Planned production order') |
| In anticipo                    | COUNTROWS(FILTER('Ordine di produzione pianificato', 'Ordine di produzione pianificato'\[Data di fine programmata\] \< 'Ordine di produzione pianificato'\[Data fabbisogno\])) |
| In ritardo                     | COUNTROWS(FILTER('Ordine di produzione pianificato', 'Ordine di produzione pianificato'\[Data di fine programmata\] \> 'Ordine di produzione pianificato'\[Data fabbisogno\])) |
| Puntuale                  | COUNTROWS(FILTER('Ordine di produzione pianificato', 'Ordine di produzione pianificato'\[Data di fine programmata\] = 'Ordine di produzione pianificato'\[Data fabbisogno\])) |
| % puntuale                | IF ( 'Ordine di produzione pianificato'\[Puntuale\] \<\> 0, 'Ordine di produzione pianificato'\[Puntuale\], IF ('Ordine di produzione pianificato'\[Tutti gli ordini pianificati\] \<\> 0, 0, BLANK()) ) / 'Ordine di produzione pianificato'\[Tutti gli ordini pianificati\] |
| Operazione completata                | COUNTROWS(FILTER('Ordine di produzione', 'Ordine di produzione'\[Dichiarata finita\] = TRUE)) |
| Percentuale articoli difettosi (ppm)     | IF( 'Ordine di produzione'\[Quantità totale\] = 0, BLANK(), (SUM('Ordine di produzione'\[Quantità difettosa\]) / 'Ordine di produzione'\[Quantità totale\]) \* 1000000) |
| Percentuale produzione ritardata  | 'Ordine di produzione'\[In ritardo \#\] / 'Ordine di produzione'\[Completato\] |
| In anticipo e completo          | COUNTROWS(FILTER('Ordine di produzione', 'Ordine di produzione'\[Completo\] = TRUE && 'Ordine di produzione'\[In anticipo\] = TRUE)) |
| Early \#                 | COUNTROWS(FILTER('Ordine di produzione', 'Ordine di produzione'\[In anticipo\] = TRUE)) |
| % in anticipo                  | IFERROR( IF('Ordine di produzione'\[In anticipo \#\] \<\> 0, 'Ordine di produzione'\[In anticipo \#\], IF('Ordine di produzione'\[Ordini totali\] = 0, BLANK(), 0)) / 'Ordine di produzione'\[Ordini totali\], BLANK()) |
| Operazione incompleta               | COUNTROWS(FILTER('Ordine di produzione', 'Ordine di produzione'\[Completo\] = FALSE && 'Ordine di produzione'\[Dichiarata finita\] = TRUE)) |
| % incompleta             | IFERROR( IF('Ordine di produzione'\[Incompleto\] \<\> 0, 'Ordine di produzione'\[Incompleto\], IF('Ordine di produzione'\[Ordini totali\] = 0, BLANK(), 0)) / 'Ordine di produzione'\[Ordini totali\], BLANK()) |
| In ritardo               | 'Ordine di produzione'\[Dichiarata finita\] = TRUE && 'Ordine di produzione'\[Valore ritardato\] = 1 |
| In anticipo                 | 'Ordine di produzione'\[Dichiarata completa\] = TRUE && 'Ordine di produzione'\[Giorni di ritardo\] \< 0 |
| Completo               | 'Ordine di produzione'\[Quantità idonea\] \>= 'Ordine di produzione'\[Quantità programmata\] |
| Dichiarata finita                | 'Ordine di produzione'\[Valore stato di produzione\] = 5 \|\| 'Ordine di produzione'\[Valore stato di produzione\] = 7 |
| In ritardo e completo           | COUNTROWS(FILTER('Ordine di produzione', 'Ordine di produzione'\[Completo\] = TRUE && 'Ordine di produzione'\[In ritardo\] = TRUE)) |
| Late \#                  | COUNTROWS(FILTER('Ordine di produzione', 'Ordine di produzione'\[In ritardo\] = TRUE)) |
| % in ritardo                   | IFERROR( IF('Ordine di produzione'\[In ritardo \#\] \<\> 0, 'Ordine di produzione'\[In ritardo \#\], IF('Ordine di produzione'\[Ordini totali\] = 0, BLANK(), 0)) / 'Ordine di produzione'\[Ordini totali\], BLANK()) |
| Puntuale e completo        | COUNTROWS(FILTER('Ordine di produzione', 'Ordine di produzione'\[Completo\] = TRUE && 'Ordine di produzione'\[In ritardo\] = FALSE && 'Ordine di produzione'\[In anticipo\] = FALSE)) |
| % puntuale e completo      | IFERROR( IF('Ordine di produzione'\[Puntuale e completo\] \<\> 0, 'Ordine di produzione'\[Puntuale e completo\], IF('Ordine di produzione'\[Completato\] = 0, BLANK(), 0)) / 'Ordine di produzione'\[Completato\], BLANK()) |
| Ordini totali             | COUNTROWS('Production order') |
| Quantità totale           | SUM('Ordine di produzione'\[Quantità idonea\]) + SUM('Ordine di produzione'\[Quantità difettosa\]) |
| Percentuale articoli difettosi (ppm)        | IF( 'Transazioni cicli di lavorazione'\[Quantità lavorata\] = 0, BLANK(), (SUM('Transazioni cicli di lavorazione'\[Quantità difettosa\]) / 'Transazioni cicli di lavorazione'\[Quantità lavorata\]) \* 1000000) |
| Percentuale articoli difettosi mista (ppm) | IF( 'Transazioni cicli di lavorazione'\[Quantità mista totale\] = 0, BLANK(), (SUM('Transazioni cicli di lavorazione'\[Quantità difettosa\]) / 'Transazioni cicli di lavorazione'\[Quantità mista totale\]) \* 1000000) |
| Quantità lavorata       | SUM('Transazioni cicli di lavorazione'\[Quantità idonea\]) + SUM('Transazioni cicli di lavorazione'\[Quantità difettosa\]) |
| Quantità mista totale     | SUM('Ordine di produzione'\[Quantità idonea\]) + SUM('Transazioni cicli di lavorazione'\[Quantità difettosa\]) |

La tabella seguente mostra le dimensioni chiave utilizzate come filtri per dividere le misure di aggregazione in modo da poter ottenere una maggiore granularità e informazioni analitiche più approfondite.

| Entità                    | Esempi di attributi                                        |
|---------------------------|---------------------------------------------------------------|
| Data dichiarazione di finito | Data di completamento (dichiarata finita), contropartita di anno e del mese                 |
| Data di fine                | Contropartita del mese mese e con stato Finito                                  |
| Data fabbisogno          | Contropartita del mese della data di fabbisogno e la data di fabbisogno            |
| Data transazione ciclo di lavorazione    | Contropartita e data del mese transazione ciclo di lavorazione:                       |
| Siti                     | ID siti, nome del sito, stato e città                          |
| Entità                  | ID e nome                                                   |
| Risorse                 | ID risorsa, nome della risorsa, tipo di risorsa e gruppo di risorse |
| Prodotti                  | Numero prodotto, nome prodotto, ID articolo e gruppo di articoli         |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
