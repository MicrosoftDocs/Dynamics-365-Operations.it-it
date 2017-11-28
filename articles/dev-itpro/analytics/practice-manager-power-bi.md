---
title: Contenuto di Power BI per responsabile procedura
description: "In questo argomento viene descritto cosa è incluso nel contenuto Power BI per il responsabile procedura. Viene descritto come accedere ai report inclusi nel contenuto e vengono fornite informazioni sul modello dati e sulle entità utilizzati per creare il contenuto."
author: KimANelson
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.assetid: 
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 3462ef1bbde9a98ac6a7bc9a5c54e58ff98559c8
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="practice-manager-power-bi-content"></a>Contenuto di Power BI per responsabile procedura

[!include[banner](../includes/banner.md)]

In questo argomento viene descritto cosa è incluso nel contenuto Microsoft Power BI per il **responsabile procedura**. Descrive come accedere ai report di Power BI e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto.

## <a name="overview"></a>Panoramica

Il contenuto di Power BI per **responsabile procedura** è stato creato per i responsabili delle procedure e i responsabili di progetto. Fornisce metriche importanti correlate ai progetti su cui l'organizzazione sta lavorando. Il dashboard fornisce una panoramica dei progetti e dei clienti correlati. Un filtro a livello di report può essere utilizzato per i report su persone giuridiche specifiche. Il contenuto di Power BI preleva i dati dalle misure aggregate di contabilità dei progetti.

Il contenuto di Power BI per **responsabile procedura** contiene cinque pagine di report: una pagina di panoramica e quattro pagine che forniscono informazioni su costi, ricavi, gestione valori ottenuti e metriche di ora del progetto suddivise in varie dimensioni.

Tutti gli importi del contenuto verranno visualizzati nella valuta di sistema. È possibile impostare la valuta di sistema nella pagina **Paramenti di sistema**.

## <a name="accessing-the-power-bi-content"></a>Accesso al contenuto Power BI
Se si utilizza Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (luglio 2017), il contenuto Power BI **Responsabile procedura** viene visualizzato nell'area di lavoro **Gestione progetti**.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Report inclusi nel contenuto Power BI

Nella seguente tabella sono descritti i dettagli sulle metriche disponibili in ogni pagina del report nel contenuto di Power BI **Responsabile procedura**.

| Pagina di report       | Metriche |
|-------------------|---------|
| Panoramica progetti | <ul><li>Progetti creati</li><li>Progetti stimati</li><li>Progetti in elaborazione</li><li>Numero di progetti per fase</li><li>Numero di progetti per città</li><li>Ricavi effettivi per cliente</li><li>Margine lordo budget per progetto</li><li>Panoramica gestione valori ottenuti</li></ul> |
| Costo              | <ul><li>Costi effettivi rispetto al budget per mese</li><li>Costi effettivi rispetto al budget per anno</li><li>Costi effettivi rispetto al budget per categoria</li><li>Costi effettivi per tipo di transazione</li></ul> |
| Ricavi           | <ul><li>Ricavi effettivi per mese</li><li>Ricavi effettivi per codice postale</li><li>Ricavi effettivi rispetto al budget per categoria</li><li>Ricavi effettivi per settore del cliente</li></ul> |
| EVM               | Indice delle prestazioni di programmazione e costo per progetto |
| Ore             | <ul><li>Ore utilizzate fatturabili effettive rispetto a ore improduttive fatturabili effettive rispetto a ore di budget</li><li>Ore utilizzate fatturabili effettive rispetto a ore improduttive fatturabili effettive per progetto</li><li>Ore utilizzate fatturabili effettive rispetto a ore improduttive fatturabili effettive per risorsa</li><li>Percentuale ore fatturabili effettive per progetto</li><li>Percentuale ore fatturabili effettive per risorsa</li></ul> |

I grafici e i riquadri in tutti i report possono essere filtrati e aggiunti al dashboard. Per ulteriori informazioni su come applicare filtri ed eseguire aggiunte in Power BI, vedere [Creare e configurare un dashboard](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards/). È inoltre possibile utilizzare la funzionalità di esportazione dati sottostanti per esportare i dati sottostanti riepilogati in una visualizzazione.

## <a name="extending-the-power-bi-content"></a>Estensione del contenuto Power BI
Utilizzando i pacchetti di contenuti disponibili in Microsoft Dynamics Lifecycle Services (LCS), è possibile fornire eccezionali analisi alle persone che non accedono a Microsoft Dynamics 365. È possibile modificare i pacchetti di contenuti affinché siano inclusi altri report o rappresentazioni e quindi pubblicarli nel tenant Power BI.com per l'analisi. 

Puoi trovare il contenuto di Power BI **Responsabile procedura** della raccolta delle risorse condivise in LCS. Per ulteriori informazioni su come scaricare il contenuto e implementarlo nell'organizzazione, vedere [Contenuto Power BI in LCS da Microsoft e dai partner](power-bi-content-microsoft-partners.md). Per guardare una demo che mostra come implementare il contenuto di Power BI, vedere [Contenuto di Power BI da Microsoft e partner in Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) (Office Mix).

Assicurarsi di scaricare il contenuto **Responsabile procedura** applicabile alla versione di Dynamics 365 in uso.

## <a name="understanding-the-data-model-and-entities"></a>Informazioni su modelli ed entità di dati

I seguenti dati vengono utilizzati per compilare le pagine di report nel contenuto Power BI **Responsabile procedura**. Questi dati vengono rappresentati come misure aggregate approntate nell'archivio entità. L'archivio entità è un database di Microsoft SQL Server che viene ottimizzato per l'analisi dei dati. Per ulteriori informazioni, vedere [Panoramica dell'integrazione di Power BI con l'archivio entità](power-bi-integration-entity-store.md).

Nelle sezioni seguenti vengono descritte le misure di aggregazione utilizzate in ciascuna entità.

### <a name="entity-projectaccountingcubeactualhourutilization"></a>Entità: ProjectAccountingCube_ActualHourUtilization
**Origine dati:** ProjEmplTrans

| Misura di aggregazione chiave      | Campo                              | descrizione | 
|--------------------------------|------------------------------------|-------------|
| Ore utilizzate fatturabili effettive | Sum(ActualUtilizationBillableRate) | Totale delle ore utilizzate fatturabili effettive. |
| Ore improduttive rispetto alle ore fatturabili effettive   | Sum(ActualBurdenBillableRate)      | Totale della percentuale effettiva improduttiva. |

### <a name="entity-projectaccountingcubeactuals"></a>Entità: ProjectAccountingCube_Actuals
**Origine dati:** ProjTransPosting

| Misura di aggregazione chiave | Campo              | descrizione | 
|---------------------------|--------------------|-------------|
| Ricavi effettivi            | Sum(ActualRevenue) | Totale dei ricavi registrati per tutte le transazioni. |   
| Costo effettivo               | Sum(ActualCost)    | Totale dei costi registrati per tutti i tipi di transazione. |

### <a name="entity-projectaccountingcubecustomer"></a>Entità: ProjectAccountingCube_Customer
**Origine dati:** CustTable

| Misura di aggregazione chiave | Campo                                            | descrizione | 
|---------------------------|--------------------------------------------------|-------------|
| Numero di progetti        | COUNTA(ProjectAccountingCube_Projects[PROJECTS]) | Numero di progetti disponibili. |


### <a name="entity-projectaccountingcubeforecasts"></a>Entità: ProjectAccountingCube_Forecasts
**Origine dati:** ProjTransBudget

| Misura di aggregazione chiave | Campo                  | descrizione | 
|---------------------------|------------------------|-------------|
| Costo budget               | Sum(BudgetCost)        | Totale dei costi previsti per tutti i tipi di transazione. |
| Ricavi budget            | Sum(BudgetRevenue)     | Totale dei ricavi maturati/fatturati di previsione.  |
| Margine lordo budget       | Sum(BudgetGrossMargin) | Differenza tra la somma dei ricavi di previsione totali e la somma dei costi di previsione totali. |

### <a name="entity-projectaccountingcubeprojectplancostsview"></a>Entità: ProjectAccountingCube_ProjectPlanCostsView
**Origine dati:** Project

| Misura di aggregazione chiave | Campo                    | descrizione | 
|---------------------------|--------------------------|-------------|
| Costo pianificato              | Sum(SumOfTotalCostPrice) | Prezzo di costo totale nelle stime per tutti i tipi di transazione di progetto con attività pianificate. |

### <a name="entity-projectaccountingcubeprojects"></a>Entità: ProjectAccountingCube_Projects
**Origine dati:** Project

| Misura di aggregazione chiave    | Campo | descrizione | 
|------------------------------|-------|-------------|
| Indice prestazioni costi       | ProjectAccountingCube_Projects[Valore ottenuto] / ProjectAccountingCube_Projects[Costo effettivo totale delle attività completate] | Calcolo del valore realizzato totale diviso per il costo effettivo totale. |
| Indice prestazioni programmazione   | ProjectAccountingCube_Projects[Valore ottenuto] / ProjectAccountingCube_Projects[Costo pianificato totale delle attività completate] | Calcolo del valore realizzato totale diviso per il costo pianificato totale. |
| Percentuale di lavoro completata | Percentuale di lavoro completato = ProjectAccountingCube_Projects[Costo effettivo totale delle attività completate] / (ProjectAccountingCube_Projects[Costo effettivo totale delle attività completate] + ProjectAccountingCube_Projects[Costo pianificato totale del progetto] - ProjectAccountingCube_Projects[Costo pianificato totale delle attività completate]) | Percentuale totale del lavoro completato ricavato dal costo effettivo totale delle attività completate e dal costo pianificato del progetto. |
| Rapporto tra ore fatturabili effettive  | ProjectAccountingCube_Projects[Ore utilizzate fatturabili effettive totali del progetto] / (ProjectAccountingCube_Projects[Ore utilizzate fatturabili effettive totali del progetto] + ProjectAccountingCube_Projects[Ore inutilizzate fatturabili effettive totali del progetto]) | Ore fatturabili effettive totali, in base alle ore utilizzate e alle ore improduttive. |
| Valore ottenuto                 | ProjectAccountingCube_Projects[Costo pianificato totale del progetto] * ProjectAccountingCube_Projects[Percentuale del lavoro completato] | Il costo pianificato totale moltiplicato per la percentuale di lavoro completato. |

### <a name="entity-projectaccountingcubetotalestimatedcosts"></a>Entità: ProjectAccountingCube_TotalEstimatedCosts 
**Origine dati:** ProjTable

| Misura di aggregazione chiave       | Campo               | descrizione | 
|---------------------------------|---------------------|-------------|
| Costo pianificato delle attività completate | Sum(TotalCostPrice) | Prezzo di costo totale nelle stime per tutti i tipi di transazione di progetto con attività completate. |

