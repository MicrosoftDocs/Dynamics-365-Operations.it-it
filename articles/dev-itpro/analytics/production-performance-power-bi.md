---
title: "Contenuto Power BI per prestazioni di produttività"
description: "In questo argomento viene descritto cosa è incluso nel contenuto Power BI per prestazioni di produttività. Descrive come accedere ai report di Power BI e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto."
author: AndersGirke
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 6e64337f19600b18320550d91c134949c33af7b0
ms.openlocfilehash: 898a1a513850024fd0164955bdd204ee4b08c632
ms.contentlocale: it-it
ms.lasthandoff: 12/01/2017

---

# <a name="production-performance-power-bi-content"></a>Contenuto Power BI per prestazioni di produttività

[!include[banner](../includes/banner.md)]

In questo argomento viene descritto cosa è incluso nel contenuto Microsoft Power BI **Prestazioni di produttività**. Descrive come accedere ai report di Power BI e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto.

## <a name="overview"></a>Panoramica

Il contenuto di Power BI **Prestazioni di produttività** è per i responsabili o gli utenti di produzione nell'organizzazione responsabili del controllo di produzione.

I report inclusi consentono di utilizzare Power BI per controllare le prestazioni delle operazioni di produzione in relazione a esecuzione puntuale, qualità e costi. I report utilizzano i dati transazionali dagli ordini di produzione e dagli ordini lotto e forniscono sia una visualizzazione aggregata delle metriche di produzione a livello aziendale e una suddivisione delle metriche per prodotto e risorsa.

Il contenuto Power BI evidenzia la capacità dell'organizzazione di completare la produzione in tempo e completamente. Le proiezioni sulle prestazioni future vengono effettuate sulla base dei piani di produzione. Report completi forniscono informazioni dettagliate dei difetti di prodotto causati dalla produzione e la percentuale di difetti per risorse e operazioni.

Il contenuto Power BI consente inoltre di analizzare gli scostamenti di produzione. Gli scostamenti di produzione vengono calcolati come la differenza tra costo stimato e costo realizzato. Gli scostamenti produzione vengono calcolati quando gli ordini di produzione o gli ordini lotto raggiungono lo stato **Finito**.

Il contenuto Power BI **Prestazioni di produttività** include dati provenienti dagli ordini di produzione e dagli ordini lotto. I report non contengono dati che siano correlati alle produzioni kanban.

## <a name="accessing-the-power-bi-content"></a>Accesso al contenuto Power BI
Il contenuto di Power BI **Prestazioni di produttività** viene visualizzato nella pagina **Prestazioni di produttività** (**Controllo produzione** > **Richieste di informazioni e report** > **Analisi delle prestazioni di produttività** > **Prestazioni di produttività**). 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Metriche incluse nel contenuto Power BI

Il contenuto di Power BI **Prestazioni di produttività** include un insieme delle pagine del report. Ciascuna pagina è costituita da un set di metriche visualizzate come grafici, riquadri e tabelle.

Nella seguente tabella viene fornita una panoramica delle visualizzazioni incluse.

| Pagina di report                                | Grafici                                               | Riquadri |
|--------------------------------------------|------------------------------------------------------|-------|
| Prestazioni di produttività                     | <ul><li>Numero di produzione per data</li><li>Numero di produzioni per prodotto e gruppo di articoli</li><li>Numero di produzioni pianificate per data</li><li>Ultimi 10 prodotti per puntuale e completo</li></ul> | <ul><li>Ordini totali</li><li>% puntuale e completo</li><li>% incompleta</li><li>% in anticipo</li><li>% in ritardo</li></ul> |
| Difetti per prodotto                         | <ul><li>Percentuale articoli difettosi (ppm) per data</li><li>Percentuale articoli difettosi (ppm) per prodotto e gruppo di articoli</li><li>Quantità prodotta per data</li><li>Primi 10 prodotti per percentuale effettiva</li></ul> | <ul><li>Percentuale articoli difettosi (ppm)</li><li>Quantità difettosa</li><li>Quantità totale</li></ul> |
| Tendenza difetti per prodotto                   | Percentuale articoli difettosi (ppm) per quantità prodotta | Percentuale articoli difettosi (ppm) |
| Difetti per risorsa                        | <ul><li>Percentuale articoli difettosi (ppm) per data</li><li>Percentuale articoli difettosi (ppm) per risorsa e sito</li><li>Percentuale articoli difettosi (ppm) per operazione</li><li>Prime 10 risorse per percentuale articoli difettosi</li></ul> | Quantità difettosa |
| Tendenza difetti per risorsa                  | Percentuale articoli difettosi (ppm) per quantità lavorata | |
| Scostamenti produzione per determinazione costi per commessa | <ul><li>Scostamento di produzione per data e tipo di gruppo di costo</li><li>Scostamento di produzione per sito e tipo di gruppo di costo</li><li>Primi 10 prodotti con scostamento di produzione sfavorevole</li><li>Primi 10 scostamenti di produzione sfavorevole per risorsa</li></ul> | <ul><li>Costo realizzato</li><li>Scostamento produzione</li><li>% scostamento di produzione</li></ul> |

## <a name="extending-the-power-bi-content"></a>Estensione del contenuto Power BI
Utilizzando i pacchetti di contenuti disponibili in Microsoft Dynamics Lifecycle Services (LCS), è possibile fornire eccezionali analisi alle persone che non accedono a Microsoft Dynamics 365. È possibile modificare i pacchetti di contenuti affinché siano inclusi altri report o rappresentazioni e quindi pubblicate i pacchetti contenuti nel tenant Power BI.com per l'analisi.

Puoi trovare il contenuto Power BI **Prestazioni di produttività** nella raccolta delle risorse condivise in LCS. Per ulteriori informazioni su come scaricare il contenuto e implementarlo nell'organizzazione, vedere [Contenuto Power BI in LCS da Microsoft e dai partner](power-bi-content-microsoft-partners.md). Per guardare una demo che mostra come implementare il contenuto di Power BI, vedere [Contenuto di Power BI da Microsoft e partner in Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) (Office Mix).

Assicurarsi di scaricare il contenuto **Prestazioni di produttività** applicabile alla versione di Dynamics 365 in uso.

> [!NOTE]
> Se si utilizza Microsoft Dynamics 365 for Operations versione 1611, KB 4011327 è un prerequisito per questo contenuto di Power BI. Dopo avere eseguito l'accesso a LCS, è possibile accedere alla KB qui: : https://fix.lcs.dynamics.com/issue/results/?q=kb4011327.

## <a name="understanding-the-data-model-and-entities"></a>Informazioni su modelli ed entità di dati

I seguenti dati vengono utilizzati per compilare le pagine di report nel contenuto Power BI **Prestazioni di produttività**. Questi dati vengono rappresentati come misure aggregate approntate nell'archivio entità. L'archivio entità è un database di Microsoft SQL Server che viene ottimizzato per l'analisi dei dati. Per ulteriori informazioni sull'archivio entità, vedere [Integrazione di Power BI con l'Archivio entità in Dynamics](power-bi-integration-entity-store.md).

La tabella seguente mostra le misure di aggregazione chiave utilizzate come base del contenuto Power BI.

| Entità                   | Misure di aggregazione chiave  | Origine dati per Finance and Operations | Campo              |
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
| Scostamento di produzione, %   | SUM('Production variance'[Production variance]) / SUM('Production variance'[Estimated cost]) |
| Tutti gli ordini pianificati       | COUNTROWS('Planned production order') |
| In anticipo                    | COUNTROWS(FILTER('Planned production order', 'Planned production order'[Scheduled end date] \< 'Planned production order'[Requirement date])) |
| In ritardo                     | COUNTROWS(FILTER('Planned production order', 'Planned production order'[Scheduled end date] \> 'Planned production order'[Requirement date])) |
| Puntuale                  | COUNTROWS(FILTER('Planned production order', 'Planned production order'[Scheduled end date] = 'Planned production order'[Requirement date])) |
| % puntuale                | IF ( 'Planned production order'[On-time] \<\> 0, 'Planned production order'[On-time], IF ('Planned production order'[All planned orders] \<\> 0, 0, BLANK()) ) / 'Planned production order'[All planned orders] |
| Completato                | COUNTROWS(FILTER('Production order', 'Production order'[Is RAF'ed] = TRUE)) |
| Percentuale articoli difettosi (ppm)     | IF( 'Production order'[Total quantity] = 0, BLANK(), (SUM('Production order'[Defective quantity]) / 'Production order'[Total quantity]) \* 1000000) |
| Percentuale produzione ritardata  | 'Production order'[Late \#] / 'Production order'[Completed] |
| In anticipo e completo          | COUNTROWS(FILTER('Production order', 'Production order'[Is in full] = TRUE && 'Production order'[Is early] = TRUE)) |
| Early \#                 | COUNTROWS(FILTER('Production order', 'Production order'[Is early] = TRUE)) |
| % in anticipo                  | IFERROR( IF('Production order'[Early \#] \<\> 0, 'Production order'[Early \#], IF('Production order'[Total orders] = 0, BLANK(), 0)) / 'Production order'[Total orders], BLANK()) |
| Incompleto               | COUNTROWS(FILTER('Production order', 'Production order'[Is in full] = FALSE && 'Production order'[Is RAF'ed] = TRUE)) |
| % incompleta             | IFERROR( IF('Production order'[Incomplete] \<\> 0, 'Production order'[Incomplete], IF('Production order'[Total orders] = 0, BLANK(), 0)) / 'Production order'[Total orders], BLANK()) |
| In ritardo               | 'Production order'[Is RAF'ed] = TRUE && 'Production order'[Delayed value] = 1 |
| In anticipo                 | 'Production order'[Is RAF'ed] = TRUE && 'Production order'[Days delayed] \< 0 |
| Completo               | 'Production order'[Good quantity] \>= 'Production order'[Scheduled quantity] |
| Dichiarata finita                | 'Production order'[Production status value] = 5 \|\| 'Production order'[Production status value] = 7 |
| In ritardo e completo           | COUNTROWS(FILTER('Production order', 'Production order'[Is in full] = TRUE && 'Production order'[Is delayed] = TRUE)) |
| Late \#                  | COUNTROWS(FILTER('Production order', 'Production order'[Is delayed] = TRUE)) |
| % in ritardo                   | IFERROR( IF('Production order'[Late \#] \<\> 0, 'Production order'[Late \#], IF('Production order'[Total orders] = 0, BLANK(), 0)) / 'Production order'[Total orders], BLANK()) |
| Puntuale e completo        | COUNTROWS(FILTER('Production order', 'Production order'[Is in full] = TRUE && 'Production order'[Is delayed] = FALSE && 'Production order'[Is early] = FALSE)) |
| % puntuale e completo      | IFERROR( IF('Production order'[On-time & in full] \<\> 0, 'Production order'[On-time & in full], IF('Production order'[Completed] = 0, BLANK(), 0)) / 'Production order'[Completed], BLANK()) |
| Ordini totali             | COUNTROWS('Production order') |
| Quantità totale           | SUM('Production order'[Good quantity]) + SUM('Production order'[Defective quantity]) |
| Percentuale articoli difettosi (ppm)        | IF( 'Route transactions'[Processed quantity] = 0, BLANK(), (SUM('Route transactions'[Defective quantity]) / 'Route transactions'[Processed quantity]) \* 1000000) |
| Percentuale articoli difettosi mista (ppm) | IF( 'Route transactions'[Total mixed quantity] = 0, BLANK(), (SUM('Route transactions'[Defective quantity]) / 'Route transactions'[Total mixed quantity]) \* 1000000) |
| Quantità lavorata       | SUM('Route transactions'[Good quantity]) + SUM('Route transactions'[Defective quantity]) |
| Quantità mista totale     | SUM('Production order'[Good quantity]) + SUM('Route transactions'[Defective quantity]) |

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

## <a name="additional-resources"></a>Risorse aggiuntive

Di seguito sono riportati alcuni collegamenti utili correlati alle entità e alla creazione di contenuto per Power BI:

- [Entità di dati](../data-entities/data-entities.md)
- [Creazione di pacchetti di contenuti per l'organizzazione](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
- [Modellazione di dati tramite Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
- [Aggiunta di riquadri Power BI ad aree di lavoro](configure-power-bi-integration.md)

