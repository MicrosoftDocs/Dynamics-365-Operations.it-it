---
title: Contenuto Power BI per la gestione dei costi
description: In questo articolo viene descritto cosa è incluso nel contenuto Power BI Gestione costi.
author: JennySong-SH
ms.date: 03/16/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom:
- "270314"
ms.assetid: 9680d977-43c8-47a7-966d-2280ba21402a
ms.search.industry: Manufacturing
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace, CostObjectWithLowestAccuracy, CostVarianceChart, CostObjectWithLowestTurn
ms.openlocfilehash: 7dcc8b2df62b250c59e343e0def5840f1b4f5432
ms.sourcegitcommit: 3c4dd125ed321af8a983e89bcb5bd6e5ed04a762
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/28/2022
ms.locfileid: "9205700"
---
# <a name="cost-management-power-bi-content"></a>Contenuto Power BI per la gestione dei costi

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>Panoramica

Il contenuto Microsoft Power BI **Gestione costi** è destinato ai contabili di inventario o agli utenti nell'organizzazione responsabili o interessati allo stato dell'inventario o WIP o ai responsabili o interessati all'analisi degli scostamenti dei costi standard.

Il contenuto Power BI si presenta in un formato strutturato in categorie che aiuta a monitorare le prestazioni degli inventari e a visualizzare il flusso dei costi. È possibile estrapolare informazioni approfondite manageriali, ad esempio l'indice di rotazione, il numero di giorni in cui l'inventario è a disposizione, la precisione e la "classificazione ABC" al livello di aggregazione preferito (società, articolo, gruppo di articoli o sito). Le informazioni disponibili possono essere utilizzate anche come supplemento dettagliato al rendiconto finanziario.

Il contenuto Power BI si basa sulla misura di aggregazione **CostObjectStatementCacheMonthly**, che ha la tabella **CostObjectStatementCache** impostata come origine dati primaria. Questa tabella viene gestita dal framework della cache del set di dati. Per impostazione predefinita, la tabella viene aggiornata ogni 24 ore, ma è possibile modificare la frequenza di aggiornamento o abilitare gli aggiornamenti manuali nella configurazione della cache dei set di dati. Gli aggiornamenti manuali possono essere eseguiti nell'area di lavoro **Amministrazione costi** è nell'area di lavoro **Analisi costo**.

Dopo ogni aggiornamento della tabella **CostObjectStatementCache**, è necessario aggiornare la misura di aggregazione **CostObjectStatementCacheMonthly** prima che vengano aggiornati i dati nelle visualizzazioni di Power BI.

## <a name="accessing-the-power-bi-content"></a>Accesso al contenuto Power BI

Il contenuto Power BI **Gestione costi** viene mostrato nelle aree di lavoro **Amministrazione costi** e **Analisi costo**.

L'area di lavoro **Amministrazione costi** contiene le schede seguenti:

- **Panoramica** - Questa scheda visualizza i dati dell'applicazione.
- **Stato contabilità inventario** - Questa scheda visualizza il contenuto di Power BI.
- **Stato contabilità produzione** - Questa scheda visualizza il contenuto di Power BI.

L'area di lavoro **Analisi costo** contiene le schede seguenti:

- **Panoramica** - Questa scheda visualizza i dati dell'applicazione.
- **Analisi contabilità inventario** - Questa scheda visualizza il contenuto di Power BI.
- **Analisi contabilità produzione** - Questa scheda visualizza il contenuto di Power BI.
- **Analisi scostamento costo standard** - Questa scheda visualizza il contenuto di Power BI.

## <a name="report-pages-that-are-included-in-the-power-bi-content"></a>Pagine di report incluse nel contenuto Power BI

Il contenuto Power BI **Gestione costi** include un set di pagine di report che consistono in un set di metriche. Queste metriche vengono visualizzate come grafici, riquadri e tabelle. 

Nelle seguenti tabelle viene fornita una panoramica delle visualizzazioni nel contenuto Power BI **Gestione costi**.

### <a name="inventory-accounting-status"></a>Stato contabilità inventario

| Pagina di report                               | Visualizzazione                                   |
|-------------------------------------------|-------------------------------------------------|
| Panoramica di Gestione articoli                        | Saldo iniziale                               |
|                                           | Modifica netto                                      |
|                                           | % modifica netto                                    |
|                                           | Saldo finale                                  |
|                                           | Precisione inventario                              |
|                                           | Indice di rotazione scorte                        |
|                                           | Scorte disponibili giornaliere                          |
|                                           | Prodotto attivo nel periodo                        |
|                                           | Oggetti di costo attivi nel periodo                   |
|                                           | Saldo per gruppo di articoli                           |
|                                           | Saldo per sito                                 |
|                                           | Rendiconto per categoria                           |
|                                           | Variazione netta per trimestre                           |
| Panoramica di magazzino per sito e per gruppo di articoli | Precisione inventario per sito                      |
|                                           | Indice di rotazione scorte per sito                |
|                                           | Saldo finale inventario per sito                |
|                                           | Precisione inventario per gruppo di articoli                |
|                                           | Indice di rotazione scorte per gruppo di articoli          |
|                                           | Saldo finale inventario per nome sito e gruppo di articoli |
| Rendiconto inventario                       | Rendiconto inventario                             |
| Rendiconto inventario per sito               | Rendiconto inventario per sito                     |
| Rendiconto inventario per categoria di prodotti  | Rendiconto inventario                             |
| Rendiconto inventario per categoria di prodotti  | Rendiconto inventario per sito                     |

### <a name="manufacturing-accounting-status"></a>Stato contabilità produzione

| Pagina di report                | Visualizzazione                       |
|----------------------------|-------------------------------------|
| Panoramica WIP da inizio anno           | Saldo iniziale                   |
|                            | Modifica netto                          |
|                            | % modifica netto                        |
|                            | Saldo finale                      |
|                            | Indice di rotazione WIP                  |
|                            | WIP giornaliero disponibile                    |
|                            | Oggetto di costo attivo nel periodo        |
|                            | Modifica netto per gruppo di risorse        |
|                            | Saldo per sito                     |
|                            | Rendiconto per categoria               |
|                            | Variazione netta per trimestre               |
| rendiconto WIP              | Saldo iniziale                   |
|                            | Saldo finale                      |
|                            | Rendiconto WIP per categoria           |
| Rendiconto WIP per sito      | Saldo iniziale                   |
|                            | Saldo finale                      |
|                            | Rendiconto WIP per categoria e sito  |
| Rendiconto WIP per gerarchia | Saldo iniziale                   |
|                            | Saldo finale                      |
|                            | Rendiconto WIP per gerarchia di categorie |

### <a name="inventory-accounting-analysis"></a>Analisi contabilità inventario

| Pagina di report        | Visualizzazione                                                                |
|--------------------|------------------------------------------------------------------------------|
| Dettagli delle scorte  | Prime 10 risorse per saldo finale                                           |
|                    | Prime 10 risorse per aumento modifica netto                                      |
|                    | Prime 10 risorse per decremento modifica netto                                      |
|                    | Prime 10 risorse per indice di rotazione scorte                                 |
|                    | Risorse per indice di rotazione scorte basso e saldo finale sopra soglia |
|                    | Prime 10 risorse per precisione bassa                                             |
| Classificazione ABC | Saldo finale inventario                                                     |
|                    | Materiale consumato                                                            |
|                    | Venduto (COGS)                                                                  |
| Tendenze scorte   | Saldo finale inventario                                                     |
|                    | Modifica netto inventario                                                         |
|                    | Indice di rotazione scorte                                                     |
|                    | Precisione inventario                                                           |

### <a name="manufacturing-accounting-analysis"></a>Analisi contabilità produzione

| Pagina di report | Visualizzazione      |
|-------------|--------------------|
| Tendenze WIP  | Saldo finale WIP |
|             | Modifica netto WIP     |
|             | Indice di rotazione WIP |

### <a name="std-cost-variance-analysis"></a>Analisi scostamento costo standard

| Pagina di report                             | Visualizzazione                                        |
|-----------------------------------------|------------------------------------------------------|
| Scostamento prezzi di acquisto (costo standard) da inizio anno | Saldo approvvigionato                                     |
|                                         | Scostamento prezzi di acquisto                              |
|                                         | Indice di scostamento prezzi di acquisto                        |
|                                         | Scostamento per gruppo di articoli                               |
|                                         | Scostamento per sito                                     |
|                                         | Prezzo di acquisto per trimestre                            |
|                                         | Prezzo di acquisto per trimestre e gruppo di articoli             |
|                                         | Prime 10 risorse per indice di prezzo di acquisto sfavorevole |
|                                         | Prime 10 risorse per indice di prezzo di acquisto favorevole   |
| Scostamento produzione (costo standard) da inizio anno     | Costo di produzione                                    |
|                                         | Scostamento produzione                                  |
|                                         | Indice di scostamento produzione                            |
|                                         | Scostamento per gruppo di articoli                               |
|                                         | Scostamento per sito                                     |
|                                         | Scostamento di produzione per trimestre                       |
|                                         | Scostamento di produzione per trimestre e tipo di scostamento     |
|                                         | Prime 10 risorse per scostamento di produzione sfavorevole  |
|                                         | Prime 10 risorse per scostamento di produzione favorevole    |

## <a name="understanding-the-data-model-and-entities"></a>Informazioni su modelli ed entità di dati

I dati dell'applicazione vengono utilizzati per compilare le pagine del report nel contenuto Power BI **Gestione costi**. Questi dati sono rappresentati come misure aggregate che vengono collocate nell'archivio entità, ovvero un database di Microsoft SQL Server ottimizzato per l'analisi. Per ulteriori informazioni, vedere [Integrazione di Power BI con l'archivio entità](power-bi-integration-entity-store.md).

Le misure di aggregazione chiave degli oggetti seguenti vengono utilizzate come base del contenuto Power BI.

| Oggetto                          | Misure di aggregazione chiave | Origine dati per la finanza e le operazioni | Campo               |
|---------------------------------|----------------------------|----------------------------------------|---------------------|
| CostObjectStatementCacheMonthly | Importo                     | CostObjectStatementCache               | Periodo              |
| CostObjectStatementCacheMonthly | Quantità                   | CostObjectStatementCache               | Qtà                 |
| CostInventoryAccountingKPIGoal  | AnnualInventoryTurn        | CostInventoryAccountingKPIGoal         | AnnualInventoryTurn |
| CostInventoryAccountingKPIGoal  | InventoryAccuracy          | CostInventoryAccountingKPIGoal         | InventoryAccuracy   |

Nella tabella seguente vengono illustrate le misure chiave calcolate nel contenuto Power BI.

| Unità di misura                            | Calcolo |
|------------------------------------|-------------|
| Saldo iniziale                  | Saldo iniziale = \[Saldo finale\]-\[Modifica netto\] |
| Qtà saldo iniziale             | Qtà saldo iniziale = \[Qtà saldo finale\]-\[Qtà modifica netto\] |
| Saldo finale                     | Saldo finale = (CALCULATE(SUM(\[Amount\]), FILTER(ALL(FiscalCalendar) ,FiscalCalendar\[MONTHSTARTDATE\] \<= MAX(FiscalCalendar\[MONTHSTARTDATE\])))) |
| Qtà saldo finale                | Qtà saldo finale = CALCULATE(SUM(\[QTY\]), FILTER(ALL(FiscalCalendar),FiscalCalendar\[MONTHSTARTDATE\] \<= MAX(FiscalCalendar\[MONTHSTARTDATE\]))) |
| Modifica netto                         | Modifica netto = SUM(\[AMOUNT\]) |
| Qtà modifica netto                    | Qtà modifica netto = SUM(\[QTY\]) |
| Indice di rotazione scorte per importo | Indice di rotazione scorte per importo = if(OR(\[Saldo medio inventario\] \<= 0, \[Inventory sold or consumed issues\] \>= 0), 0, ABS(\[Inventario venduto o uscite consumate\])/\[Inventario venduto o uscite consumate\]) |
| Saldo medio inventario          | Saldo medio inventario = ((\[Saldo finale\] + \[Saldo iniziale\]) / 2) |
| Scorte disponibili giornaliere             | Scorte disponibili giornaliere = 365 / CostObjectStatementEntries\[Indice di rotazione scorte per importo\] |
| Precisione inventario                 | Precisione inventario per importo = IF(\[Saldo finale\] \<= 0, IF(OR(\[Inventory counted amount\] \<\> 0, \[Saldo finale\] \< 0), 0, 1), MAX(0, (\[Saldo finale\] - ABS(\[Importo conteggiato inventario\]))/\[Saldo finale\])) |

La seguenti dimensioni chiave vengono utilizzate come filtri per dividere le misure di aggregazione in modo da poter ottenere una maggiore granularità e informazioni analitiche più approfondite.


| Entità                                                  | Esempi di attributi                          |
|---------------------------------------------------------|-------------------------------------------------|
| Prodotti                                                | Numero prodotto, nome prodotto, unità, gruppi di articoli |
| Gerarchie di categorie (assegnate al ruolo Gestione costi) | Gerarchia di categorie, livello di categoria              |
| Persone giuridiche                                          | Nomi di persone giuridiche                              |
| Calendari fiscali                                        | Calendario fiscale, anno, trimestre, periodo, mese   |
| Sito                                                    | ID, nome, indirizzo, Stato/regione, paese               |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

