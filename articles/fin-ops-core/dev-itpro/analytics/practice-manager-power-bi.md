---
title: Contenuto di Power BI per responsabile procedura
description: In questo articolo viene descritto cosa è incluso nel contenuto Power BI Responsabile procedura.
author: sericks007
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.assetid: ''
ms.search.form: ProjManagementWorkspace
ms.openlocfilehash: 92c2881c89da0b23e3a66c0f8bbcafd91c38c6e3
ms.sourcegitcommit: 3c4dd125ed321af8a983e89bcb5bd6e5ed04a762
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206506"
---
# <a name="practice-manager-power-bi-content"></a>Contenuto di Power BI per responsabile procedura

[!include [banner](../includes/banner.md)]

In questo articolo viene descritto cosa è incluso nel contenuto Microsoft Power BI **Responsabile procedura**. Descrive come accedere ai report di Power BI e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto.

## <a name="overview"></a>Panoramica

Il contenuto Power BI **Responsabile procedura** è stato creato per i responsabili delle procedure e i responsabili di progetto. Fornisce metriche importanti correlate ai progetti su cui l'organizzazione sta lavorando. Il dashboard fornisce una panoramica dei progetti e dei clienti correlati. Un filtro a livello di report può essere utilizzato per i report su persone giuridiche specifiche. Il contenuto di Power BI preleva i dati dalle misure aggregate di contabilità dei progetti.

Il contenuto di Power BI **Responsabile procedura** contiene cinque pagine di report: una pagina di panoramica e quattro pagine che forniscono informazioni su costi, ricavi, gestione valori ottenuti e metriche di ora del progetto suddivise in varie dimensioni.

Tutti gli importi del contenuto verranno visualizzati nella valuta di sistema. È possibile impostare la valuta di sistema nella pagina **Paramenti di sistema**.

## <a name="accessing-the-power-bi-content"></a>Accesso al contenuto Power BI

Il contenuto di Power BI **Responsabile procedura** viene visualizzato nell'area di lavoro **Gestione progetti**.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Report inclusi nel contenuto Power BI

Nella seguente tabella sono descritti i dettagli sulle metriche disponibili in ogni pagina del report nel contenuto di Power BI **Responsabile procedura**.

| Pagina di report       | Metriche |
|-------------------|---------|
| Panoramica progetti | <ul><li>Progetti creati</li><li>Progetti stimati</li><li>Progetti in elaborazione</li><li>Ricavi effettivi per cliente</li><li>Margine lordo budget per progetto</li><li>Panoramica gestione valori ottenuti</li></ul> |
| Costo              | <ul><li>Costi effettivi rispetto al budget per mese</li><li>Costi effettivi rispetto al budget per anno</li><li>Costi effettivi rispetto al budget per categoria</li><li>Costi effettivi per tipo di transazione</li></ul> |
| Ricavi           | <ul><li>Ricavi effettivi per mese</li><li>Ricavi effettivi per codice postale</li><li>Ricavi effettivi rispetto al budget per categoria</li><li>Ricavi effettivi per settore del cliente</li></ul> |
| EVM               | Indice delle prestazioni di programmazione e costo per progetto |
| Ore             | <ul><li>Ore utilizzate fatturabili effettive rispetto a ore improduttive fatturabili effettive rispetto a ore di budget</li><li>Ore utilizzate fatturabili effettive rispetto a ore improduttive fatturabili effettive per progetto</li><li>Ore utilizzate fatturabili effettive rispetto a ore improduttive fatturabili effettive per risorsa</li><li>Percentuale ore fatturabili effettive per progetto</li><li>Percentuale ore fatturabili effettive per risorsa</li></ul> |

I grafici e i riquadri in tutti i report possono essere filtrati e aggiunti al dashboard. Per ulteriori informazioni su come applicare filtri ed eseguire aggiunte in Power BI, vedere [Creare e configurare un dashboard](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards/) È inoltre possibile utilizzare la funzionalità di esportazione dati sottostanti per esportare i dati sottostanti riepilogati in una visualizzazione.

## <a name="understanding-the-data-model-and-entities"></a>Informazioni su modelli ed entità di dati

I seguenti dati vengono utilizzati per compilare le pagine di report nel contenuto Power BI **Responsabile procedura**. Questi dati vengono rappresentati come misure aggregate approntate nell'archivio entità. L'archivio entità è un database di Microsoft SQL Server che viene ottimizzato per l'analisi dei dati. Per ulteriori informazioni, vedere [Integrazione di Power BI con l'archivio entità](power-bi-integration-entity-store.md).

Nelle sezioni seguenti vengono descritte le misure di aggregazione utilizzate in ciascuna entità.

### <a name="entity-projectaccountingcube_actualhourutilization"></a>Entità: ProjectAccountingCube\_ActualHourUtilization
**Origine dati:** ProjEmplTrans

| Misura di aggregazione chiave      | Campo                              | Descrizione |
|--------------------------------|------------------------------------|-------------|
| Ore utilizzate fatturabili effettive | Sum(ActualUtilizationBillableRate) | Totale delle ore utilizzate fatturabili effettive. |
| Ore improduttive rispetto alle ore fatturabili effettive   | Sum(ActualBurdenBillableRate)      | Totale della percentuale effettiva improduttiva. |

### <a name="entity-projectaccountingcube_actuals"></a>Entità: ProjectAccountingCube\_Actuals
**Origine dati:** ProjTransPosting

| Misura di aggregazione chiave | Campo              | Descrizione |
|---------------------------|--------------------|-------------|
| Ricavi effettivi            | Sum(ActualRevenue) | Totale dei ricavi registrati per tutte le transazioni. |
| Costo effettivo               | Sum(ActualCost)    | Totale dei costi registrati per tutti i tipi di transazione. |

### <a name="entity-projectaccountingcube_customer"></a>Entità: ProjectAccountingCube\_Customer
**Origine dati:** CustTable

| Misura di aggregazione chiave | Campo                                             | Descrizione |
|---------------------------|---------------------------------------------------|-------------|
| Numero di progetti        | COUNTA(ProjectAccountingCube\_Projects\[PROJECTS\]) | Numero di progetti disponibili. |

### <a name="entity-projectaccountingcube_forecasts"></a>Entità: ProjectAccountingCube\_Forecasts
**Origine dati:** ProjTransBudget

| Misura di aggregazione chiave | Campo                  | Descrizione |
|---------------------------|------------------------|-------------|
| Costo budget               | Sum(BudgetCost)        | Totale dei costi previsti per tutti i tipi di transazione. |
| Ricavi budget            | Sum(BudgetRevenue)     | Totale dei ricavi maturati/fatturati di previsione. |
| Margine lordo budget       | Sum(BudgetGrossMargin) | Differenza tra la somma dei ricavi di previsione totali e la somma dei costi di previsione totali. |

### <a name="entity-projectaccountingcube_projectplancostsview"></a>Entità: ProjectAccountingCube\_ProjectPlanCostsView
**Origine dati:** Project

| Misura di aggregazione chiave | Campo                    | Descrizione |
|---------------------------|--------------------------|-------------|
| Costo pianificato              | Sum(SumOfTotalCostPrice) | Prezzo di costo totale nelle stime per tutti i tipi di transazione di progetto con attività pianificate. |

### <a name="entity-projectaccountingcube_projects"></a>Entità: ProjectAccountingCube\_Projects
**Origine dati:** Project

| Misura di aggregazione chiave    | Campo | Descrizione |
|------------------------------|-------|-------------|
| Indice prestazioni costi       | ProjectAccountingCube\_Projects\[Valore ottenuto\] ÷ ProjectAccountingCube\_Projects\[Costo effettivo totale delle attività completate\] | Calcolo del valore realizzato totale diviso per il costo effettivo totale. |
| Indice prestazioni programmazione   | ProjectAccountingCube\_Projects\[Valore ottenuto\] ÷ ProjectAccountingCube\_Projects\[Costo pianificato totale delle attività completate\] | Calcolo del valore realizzato totale diviso per il costo pianificato totale. |
| Percentuale di lavoro completata | Percentuale di lavoro completato = ProjectAccountingCube\_Projects\[Costo effettivo totale delle attività completate\] ÷ (ProjectAccountingCube\_Projects\[Costo effettivo totale delle attività completate\] + ProjectAccountingCube\_Projects\[Costo pianificato totale di progetto\] – ProjectAccountingCube\_Projects\[Costo pianificato totale delle attività completate\]) | Percentuale totale del lavoro completato ricavato dal costo effettivo totale delle attività completate e dal costo pianificato del progetto. |
| Rapporto tra ore fatturabili effettive  | ProjectAccountingCube\_Projects\[Ore utilizzate fatturabili effettive totali del progetto\] ÷ (ProjectAccountingCube\_Projects\[Ore utilizzate fatturabili effettive totali del progetto\] + ProjectAccountingCube\_Projects\[Ore improduttive fatturabili effettive totali del progetto\]) | Ore fatturabili effettive totali, in base alle ore utilizzate e alle ore improduttive. |
| Valore ottenuto                 | ProjectAccountingCube\_Projects\[Costo pianificato totale del progetto\] × ProjectAccountingCube\_Projects\[Percentuale di lavoro completato\] | Il costo pianificato totale moltiplicato per la percentuale di lavoro completato. |

### <a name="entity-projectaccountingcube_totalestimatedcosts"></a>Entità: ProjectAccountingCube\_TotalEstimatedCosts 
**Origine dati:** ProjTable

| Misura di aggregazione chiave       | Campo               | Descrizione |
|---------------------------------|---------------------|-------------|
| Costo pianificato delle attività completate | Sum(TotalCostPrice) | Prezzo di costo totale nelle stime per tutti i tipi di transazione di progetto con attività completate. |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
