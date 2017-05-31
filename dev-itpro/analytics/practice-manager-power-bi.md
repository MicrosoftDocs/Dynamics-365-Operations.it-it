---
title: Contenuto di Power BI per responsabile procedura
description: "In questo argomento viene descritto cosa è incluso nel contenuto Power BI per il responsabile procedura. Viene descritto come accedere ai report inclusi nel pacchetto di contenuti e vengono fornite informazioni sul modello dati e sulle entità utilizzati per creare il pacchetto di contenuti."
author: knelson
manager: AnnBe
ms.date: 04/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer/IT Pro
ms.assetid: 
ms.search.region: Global
ms.author: knelson
ms.dyn365.intro: 2017/04/27
ms.dyn365.version: 
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 0f2a1a9df8e5036c60b74b8a710e606b0b1e312a
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="practice-manager-power-bi-content"></a>Contenuto di Power BI per responsabile procedura

[!include[banner](../includes/banner.md)]


In questo argomento viene descritto cosa è incluso nel contenuto Microsoft Power BI per il **responsabile procedura**. Descrive come accedere ai report di Power BI e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto.

## <a name="overview"></a>Panoramica

Il contenuto di Power BI per **responsabile procedura** è stato creato per i responsabili delle procedure e i responsabili di progetto. Fornisce metriche importanti correlate ai progetti su cui l'organizzazione sta lavorando. Il dashboard fornisce una panoramica dei progetti e dei clienti correlati. Un filtro a livello di report può essere utilizzato per i report su persone giuridiche specifiche. Il contenuto di Power BI esegue il pull dei dati dalle misure di aggregazione della contabilità dei progetti per Microsoft Dynamics 365 for Operations.

Il contenuto di Power BI per **responsabile procedura** contiene cinque pagine di report: una pagina di panoramica e quattro pagine che forniscono informazioni su costi, ricavi, gestione valori ottenuti e metriche di ora del progetto suddivise in varie dimensioni.

Tutti gli importi del contenuto verranno visualizzati nella valuta di sistema. È possibile impostare la valuta di sistema nella pagina **Paramenti di sistema**.

## <a name="accessing-the-power-bi-content"></a>Accesso al contenuto Power BI

È possibile trovare il contenuto Power BI per il **Responsabile procedura** nella libreria delle risorse condivise in Microsoft Dynamics Lifecycle Services (LCS). Per ulteriori informazioni su come scaricare il pacchetto di contenuto e collegarlo ai dati Dynamics 365 for Operations, vedere [Contenuto Power BI in LCS da Microsoft e dai partner](power-bi-content-microsoft-partners.md).

Per guardare una demo che mostra come implementare il contenuto di Power BI, vedere [Contenuto di Power BI da Microsoft e partner in Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) (Office Mix).

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Report inclusi nel contenuto Power BI

Nella seguente tabella sono descritti i dettagli sulle metriche disponibili in ogni pagina del report nel contenuto di Power BI **Responsabile procedura**.

| Pagina di report                                          | Metriche               |
|------------------------------------------------------|-----------------------------------------------|
| Dashboard  | Progetti creati<br>Progetti stimati<br>Progetti in elaborazione<br>Numero di progetti per fase<br>Numero di progetti per città<br>Ricavi effettivi per cliente<br>Margine lordo budget per progetto<br>Panoramica gestione valori ottenuti |
| Costo                                                 | Costi effettivi rispetto al budget per mese<br>Costi effettivi rispetto al budget per anno<br>Costi effettivi rispetto al budget per categoria<br>Costi effettivi per tipo di transazione       |
| Ricavi                                              | Ricavi effettivi per mese<br>Ricavi effettivi per codice postale<br>Ricavi effettivi rispetto al budget per categoria<br>Ricavi effettivi per settore del cliente        |
| EVM                                                  | Indice delle prestazioni di programmazione e costo per progetto                 |
| Ore                                                | Ore utilizzate fatturabili effettive rispetto a ore improduttive fatturabili effettive rispetto a ore di budget<br>Ore utilizzate fatturabili effettive rispetto a ore improduttive fatturabili effettive per progetto<br>Ore utilizzate fatturabili effettive rispetto a ore improduttive fatturabili effettive per risorsa<br>Percentuale ore fatturabili effettive per progetto<br>Percentuale ore fatturabili effettive per risorsa |

I grafici e i riquadri in tutti i report possono essere filtrati e aggiunti al dashboard. Per ulteriori informazioni su come applicare filtri ed eseguire aggiunte in Power BI, vedere [Creare e configurare un dashboard](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards/). È inoltre possibile utilizzare la funzionalità di esportazione dati sottostanti per esportare i dati sottostanti riepilogati in una visualizzazione.

## <a name="understanding-the-data-model-and-entities"></a>Informazioni su modelli ed entità di dati

I dati di Dynamics 365 for Operations vengono utilizzati per compilare le pagine di report nel contenuto Power BI per il **responsabile procedura**. Questi dati sono rappresentati come misure aggregate che vengono collocate nell'archivio entità, ovvero un database di Microsoft SQL ottimizzato per l'analisi. Per ulteriori informazioni, vedere [Panoramica dell'integrazione di Power BI con l'archivio entità](power-bi-integration-entity-store.md).

Nelle sezioni seguenti vengono illustrate le misure di aggregazione utilizzate in ciascuna entità.

### <a name="entity-projectaccountingcubeactualhourutilization"></a>Entità: ProjectAccountingCube_ActualHourUtilization
**Origine dati**: ProjEmplTrans

| Misura di aggregazione chiave                | Campo                                | descrizione                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
| ActualBillableUtilizedHours              | Sum(ActualUtilizationBillableRate)   | Totale delle ore utilizzate fatturabili effettive |
| ActualBillableBurdenHours                | Sum(ActualBurdenBillableRate)        | Totale della percentuale effettiva improduttiva             |

### <a name="entity-projectaccountingcubeactuals"></a>Entità: ProjectAccountingCube_Actuals
**Origine dati**: ProjTransPosting

| Misura di aggregazione chiave                | Campo                                | descrizione                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
| ActualRevenue                            |     Sum(ActualRevenue)               |  Totale dei ricavi registrati per qualsiasi transazione |   
| ActualCost   |                             Sum(ActualCost)           |    Totale dei costi registrati per tutti i tipi di transazione    |

### <a name="entity-projectaccountingcubecustomer"></a>Entità: ProjectAccountingCube_Customer
**Origine dati**: CustTable

| Misura di aggregazione chiave                | Campo                                | descrizione                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
|    Numero di progetti        |   COUNTA(ProjectAccountingCube_Projects[PROJECTS])       |         Numero di progetti disponibili    |


### <a name="entity-projectaccountingcubeforecasts"></a>Entità: ProjectAccountingCube_Forecasts
**Origine dati**: ProjTransBudget

| Misura di aggregazione chiave                | Campo                                | descrizione                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
|    BudgetCost    |       Sum(BudgetCost)  |       Totale dei costi previsti per tutti i tipi di transazione     |
|     BudgetRevenue    |         Sum(BudgetRevenue)    |    Totale dei ricavi maturati/fatturati di previsione         |
|BudgetGrossMargin | Sum(BudgetGrossMargin) |Differenza tra la somma dei ricavi di previsione totali e la somma dei costi di previsione totali

### <a name="entity-projectaccountingcubeprojectplancostsview"></a>Entità: ProjectAccountingCube_ProjectPlanCostsView
**Origine dati**: Project

| Misura di aggregazione chiave                | Campo                                | descrizione                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
|      PlannedCost      |        Sum(SumOfTotalCostPrice)   | Prezzo di costo totale nelle stime per tutti i tipi di transazione di progetto con attività pianificate |

### <a name="entity-projectaccountingcubeprojects"></a>Entità: ProjectAccountingCube_Projects
**Origine dati**: Project

| Misura di aggregazione chiave                | Campo                                | descrizione                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
|   Indice prestazioni costi  |ProjectAccountingCube_Projects[Valore ottenuto] / ProjectAccountingCube_Projects[Costo effettivo totale delle attività completate] |     Calcolo del valore realizzato totale diviso per il costo effettivo totale|
|  Indice prestazioni programmazione |ProjectAccountingCube_Projects[Valore ottenuto] / ProjectAccountingCube_Projects[Costo pianificato totale delle attività completate]|Calcolo del valore realizzato totale diviso per il costo pianificato totale |
|Percentuale di lavoro completata |Percentuale di lavoro completato = ProjectAccountingCube_Projects[Costo effettivo totale delle attività completate] / (ProjectAccountingCube_Projects[Costo effettivo totale delle attività completate] + ProjectAccountingCube_Projects[Costo pianificato totale del progetto] - ProjectAccountingCube_Projects[Costo pianificato totale delle attività completate])|Percentuale totale del lavoro completato ricavato dal costo effettivo totale dell'attività completata e dal costo pianificato del progetto|
|Percentuale ore fatturabili effettive del progetto|ProjectAccountingCube_Projects[Ore utilizzate fatturabili effettive totali del progetto] / (ProjectAccountingCube_Projects[Ore utilizzate fatturabili effettive totali del progetto] + ProjectAccountingCube_Projects[Ore inutilizzate fatturabili effettive totali del progetto])|Ore fatturabili effettive totali utilizzate e improduttive|
|Valore ottenuto|ProjectAccountingCube_Projects[Costo pianificato totale del progetto] * ProjectAccountingCube_Projects[Percentuale del lavoro completato]|Il costo pianificato totale moltiplicato per la percentuale di lavoro completato|

### <a name="entity-projectaccountingcubetotalestimatedcosts"></a>Entità: ProjectAccountingCube_TotalEstimatedCosts 
**Origine dati**: ProjTable

| Misura di aggregazione chiave                | Campo                                | descrizione                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
| CompletedActivityPlannedCost  |  Sum(TotalCostPrice)  |   Prezzo di costo totale nelle stime per tutti i tipi di transazione di progetto con attività completate|

## <a name="additional-resources"></a>Risorse aggiuntive

Di seguito sono riportati alcuni collegamenti utili correlati alle entità e alla creazione di contenuto per Power BI:

- [Entità di dati](/dynamics365/operations/dev-itpro/data-entities/data-entities)
- [Creazione di pacchetti di contenuti per l'organizzazione](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
- [Modellazione di dati tramite Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
- [Configurare l'integrazione di Power BI per aree di lavoro](configure-power-bi-integration.md)

